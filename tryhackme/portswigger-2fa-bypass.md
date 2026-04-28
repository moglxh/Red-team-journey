# PortSwigger Lab - 2FA Simple Bypass

## Vulnerability
Improper implementation of two-factor authentication (2FA)

## Description
The application implemented a 2FA mechanism, but it could be bypassed due to flawed logic in the authentication flow.

## What I did
- Observed the login and 2FA process
- Identified a flaw in how the application validated the second factor
- Bypassed the 2FA step to gain access without proper verification

## Key Learning
- 2FA does not guarantee security if implemented incorrectly
- Authentication flows must be validated end-to-end
- Logic flaws can completely break security mechanisms

## Impact
An attacker can bypass the second authentication factor and gain unauthorized access to user accounts.

## Fix
- Enforce proper server-side validation of 2FA
- Ensure all authentication steps are mandatory and cannot be skipped
- Validate session state before granting access
