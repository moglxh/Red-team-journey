# trust_graph.md

## Target

Scheduled Task: logrotate

```
logrotate.timer
    ↓
logrotate.service
    ↓
/usr/sbin/logrotate
```

---

## Trigger

Timer:

```
logrotate.timer
```

Purpose:

```
Scheduled execution at configured intervals.
```

Activation Flow:

```
Time Event
    ↓
systemd
    ↓
logrotate.timer
```

---

## Execution Identity

Typical Identity:

```
root
```

Reason:

```
Log files belong to many different users and services.

The process requires elevated privileges to read, rename,
compress, and remove system logs.
```

---

## Service

Service Unit:

```
logrotate.service
```

Role:

```
Provides execution policy.

Defines:
- ExecStart
- User
- Group
- Environment
- Security restrictions
```

Flow:

```
logrotate.timer
    ↓
logrotate.service
```

---

## Executable

Executable:

```
/usr/sbin/logrotate
```

Purpose:

```
Manage log rotation.

Read configuration.
Rotate logs.
Compress old logs.
Remove expired logs.
```

Flow:

```
logrotate.service
    ↓
/usr/sbin/logrotate
```

---

## Dependencies

### Configuration

```
/etc/logrotate.conf
/etc/logrotate.d/*
```

### Runtime Programs

Examples:

```
gzip
systemd
libc
```

### Data Sources

Examples:

```
/var/log/auth.log
/var/log/syslog
```

### Filesystem

Required for:

```
Read
Write
Rename
Delete
Compress
```

Dependency Graph:

```
logrotate
│
├── systemd
├── libc
├── configuration
├── filesystem
└── log files
```

---

## Resources

### CPU

Used during:

```
Compression
File processing
```

### Memory

Used during:

```
Configuration parsing
Runtime execution
```

### Disk

Used for:

```
Reading logs
Writing rotated logs
Compression output
```

### Files

Examples:

```
/var/log/*
```

Resource Graph:

```
logrotate
│
├── CPU
├── Memory
├── Disk
└── Log Files
```

---

## Authority Flow

Authority originates from:

```
root
```

Flow:

```
root
    ↓
systemd
    ↓
logrotate.service
    ↓
/usr/sbin/logrotate
```

Meaning:

```
Root authority is delegated through systemd
into the executable.
```

---

## Trust Relationships

The executable trusts:

### Configuration

```
/etc/logrotate.conf
/etc/logrotate.d/*
```

### Runtime Libraries

```
libc
other shared libraries
```

### Filesystem State

```
Paths exist
Permissions are valid
Files behave normally
```

### Helper Programs

```
gzip
other invoked utilities
```

Trust Graph:

```
logrotate
│
├── trusts configuration
├── trusts filesystem
├── trusts libraries
└── trusts helper programs
```

---

## Influence Surfaces

Influence means:

```
Something capable of changing behavior.
```

### Timer Configuration

Influences:

```
When execution occurs
```

### Service Configuration

Influences:

```
Execution policy
Identity
Environment
```

### Configuration Files

Influence:

```
Rotation behavior
Retention policy
Target files
```

### Log Files

Influence:

```
Program decisions
Rotation actions
```

### Runtime Environment

Influence:

```
Environment variables
Filesystem state
```

Influence Graph:

```
Timer
    │
    ▼
Service
    │
    ▼
Executable
    ▲
    │
    ├── Config Files
    ├── Log Files
    ├── Environment
    └── Filesystem State
```

---

## Final System Model

```
Time
    ↓
logrotate.timer
    ↓
logrotate.service
    ↓
/usr/sbin/logrotate

Authority:
root

Dependencies:
systemd
configuration
libraries
filesystem
log files

Resources:
CPU
memory
disk
files

Trust:
configuration
libraries
filesystem
helper programs

Influence:
timer settings
service settings
configuration
runtime environment
filesystem state
```

## Key Observation

This document does not attempt to identify vulnerabilities.

It answers:

* What executes?
* Under whose authority?
* What does it depend on?
* What does it trust?
* What can influence it?

That is the foundation of system modeling.
