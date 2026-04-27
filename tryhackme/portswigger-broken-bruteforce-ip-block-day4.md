# PortSwigger Lab - Broken Brute-Force Protection (IP Block)

## Vulnerability
Weak brute-force protection mechanism based on IP blocking

## Description
The application attempted to prevent brute-force attacks by blocking IP addresses after multiple failed login attempts. However, the protection was ineffective and could be bypassed.

## What I did
- Observed the login behavior and IP-based restrictions
- Identified how the blocking mechanism worked
- Bypassed the protection to continue testing login attempts
- Successfully identified valid credentials and accessed the account

## Key Learning
- Security controls like IP blocking can be ineffective if not implemented properly
- Attackers can often bypass protections with simple techniques
- Testing defenses is just as important as finding vulnerabilities

## Impact
An attacker can bypass brute-force protection and attempt multiple login attempts, increasing the risk of account compromise.

## Fix
- Implement stronger rate limiting (per account, not just IP)
- Use CAPTCHA or multi-factor authentication
- Monitor and block suspicious behavior effectively
