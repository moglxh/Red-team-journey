# PortSwigger Labs - File Path Traversal Bypasses

## Labs Completed
- File path traversal, traversal sequences stripped non-recursively
- File path traversal, traversal sequences stripped with superfluous URL-decode
- File path traversal, validation of start of path

## Vulnerability
File Path Traversal

## Description
The application improperly handled user-controlled file paths, allowing attackers to access files outside the intended directory. Various filter and validation mechanisms were bypassed using encoding and traversal manipulation techniques.

## What I learned
- Bypassing non-recursive traversal stripping
- Exploiting URL decoding inconsistencies
- Circumventing weak path validation logic
- Understanding canonicalization and normalization issues

## Key Learning
- Blacklist-style filtering is unreliable
- Input normalization and decoding behavior matter greatly
- Weak path validation can often be bypassed through crafted payloads

## Impact
An attacker may access sensitive files on the server, potentially exposing credentials, configuration files, or system information.

## Fix
- Use strict allowlists for file access
- Canonicalize paths before validation
- Restrict file access to intended directories only
- Avoid relying on blacklist filtering
