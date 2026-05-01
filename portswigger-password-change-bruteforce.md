# PortSwigger Lab - Password Brute-Force via Password Change

## Vulnerability
Brute-force vulnerability in password change functionality

## Description
The application’s password change feature lacked proper protections, allowing attackers to attempt multiple password guesses without sufficient restrictions.

## What I did
- Analyzed the password change request and behavior
- Identified lack of rate limiting or proper validation
- Used a list of candidate passwords to perform brute-force attempts
- Successfully identified the correct password and accessed the account

## Key Learning
- Brute-force protections must be applied across all authentication-related features, not just login
- Overlooking secondary functionalities can introduce serious vulnerabilities
- Consistent security controls are essential

## Impact
An attacker can brute-force user credentials through alternative entry points, leading to unauthorized account access.

## Fix
- Implement rate limiting on all sensitive endpoints
- Enforce strong password policies
- Monitor and block repeated failed attempts
