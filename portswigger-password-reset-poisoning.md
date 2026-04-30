# PortSwigger Lab - Password Reset Poisoning via Middleware

## Vulnerability
Password reset poisoning via improper handling of request headers (middleware trust issue)

## Description
The application used user-controlled input (such as headers) when generating password reset links. This allowed manipulation of the reset URL sent to the victim, enabling an attacker to intercept or control the reset process.

## What I did
- Analyzed the password reset functionality and email flow
- Identified that request data was used to construct reset links
- Manipulated the request so the reset link pointed to an attacker-controlled location
- Captured the reset token from the victim’s interaction
- Used the token to reset the victim’s password and access the account

## Key Learning
- Applications should not trust user-controlled headers when generating sensitive links
- Password reset functionality is a critical attack surface
- Middleware misconfigurations can introduce serious vulnerabilities

## Impact
An attacker can hijack password reset links and gain unauthorized access to user accounts, leading to full account takeover.

## Fix
- Do not use user-controlled input (e.g., headers) to construct reset URLs
- Use a fixed, trusted domain for all password reset links
- Validate and sanitize all incoming request data
