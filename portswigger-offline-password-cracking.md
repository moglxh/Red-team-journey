# PortSwigger Lab - Offline Password Cracking

## Vulnerability
Insecure storage of password hash in a cookie combined with XSS vulnerability

## Description
The application stored a user's password hash inside a cookie and also contained an XSS vulnerability. This allowed extraction of the cookie, followed by offline password cracking to recover the user's credentials.

## What I did
- Identified an XSS vulnerability in the comment functionality
- Used the vulnerability to obtain the victim’s authentication cookie
- Extracted the password hash from the cookie
- Performed offline password cracking to recover the plaintext password
- Logged in as the victim and accessed the account

## Key Learning
- Sensitive data like password hashes should never be exposed to the client
- XSS vulnerabilities can lead to full account compromise
- Offline attacks are powerful when attackers obtain hashed credentials

## Impact
An attacker can steal authentication data and crack passwords offline, leading to complete account takeover.

## Fix
- Never store sensitive information like password hashes in cookies
- Prevent XSS vulnerabilities through proper input validation and output encoding
- Use secure session management mechanisms
