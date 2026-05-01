# PortSwigger Lab - Broken Brute-Force Protection (Multiple Credentials per Request)

## Vulnerability
Ineffective brute-force protection allowing multiple credential attempts per request

## Description
The application attempted to limit brute-force attacks but failed to properly handle multiple credential submissions within a single request, allowing attackers to bypass restrictions.

## What I did
- Analyzed the login request structure
- Identified that multiple credentials could be tested in one request
- Used this behavior to bypass brute-force protections
- Successfully identified valid credentials and accessed the account

## Key Learning
- Brute-force protections must consider all possible attack patterns
- Attackers can optimize requests to bypass rate limiting
- Security controls must validate input thoroughly

## Impact
An attacker can bypass brute-force protections and test multiple credentials efficiently, increasing the risk of account compromise.

## Fix
- Enforce strict validation of request structure
- Apply rate limiting per credential attempt, not just per request
- Detect and block abnormal request patterns
