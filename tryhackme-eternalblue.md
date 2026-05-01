# TryHackMe - Hacking into Windows via EternalBlue

## Vulnerability
EternalBlue (MS17-010) - SMB Remote Code Execution

## Description
EternalBlue is a critical vulnerability in Microsoft's SMB protocol that allows remote attackers to execute code on vulnerable systems without authentication.

## What I did
- Identified the target running a vulnerable SMB service
- Used Metasploit to exploit the EternalBlue vulnerability
- Gained remote access to the Windows system
- Explored the system post-exploitation

## Key Learning
- Unpatched systems can be critically vulnerable
- SMB (port 445) is a high-value target in network attacks
- Exploitation frameworks can simplify complex attacks

## Impact
An attacker can gain full control over a vulnerable system remotely, leading to data loss, lateral movement, or complete network compromise.

## Fix
- Apply security patches (MS17-010)
- Disable SMBv1 if not required
- Restrict access to SMB ports (445)
