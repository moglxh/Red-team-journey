# PortSwigger Lab - Brute-Forcing a Stay Logged-In Cookie

## Vulnerability
Weak implementation of "stay logged-in" functionality using predictable cookies

## Description
The application used a cookie to keep users logged in across sessions. However, the cookie value was weakly generated and could be brute-forced to gain access to another user's account.

## What I did
- Analyzed the stay logged-in cookie behavior
- Identified that the cookie value was predictable
- Performed brute-force attempts on the cookie
- Successfully generated a valid cookie for another user and accessed their account

## Key Learning
- Authentication tokens must be securely generated and unpredictable
- Weak cookie mechanisms can lead to account takeover
- Session management is a critical part of web security

## Impact
An attacker can brute-force authentication cookies and gain unauthorized access to user accounts without needing login credentials.

## Fix
- Use strong, random, and securely generated session tokens
- Avoid predictable or reversible cookie values
- Implement proper session management and expiration
