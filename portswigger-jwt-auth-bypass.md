# PortSwigger Labs - JWT Authentication Bypass

## Labs Completed
- JWT authentication bypass via unverified signature
- JWT authentication bypass via flawed signature verification

## Vulnerability
JWT Authentication Misconfiguration

## Description
The application improperly validated JWT signatures, allowing authentication bypass through manipulated or unsigned tokens.

## What I learned
- Understanding JWT structure and components
- Exploiting applications that accept unsigned tokens
- Bypassing flawed signature verification logic
- Modifying token claims to manipulate authentication behavior

## Key Learning
- JWT signatures must always be strictly verified
- Applications should never trust unsigned or improperly validated tokens
- Weak JWT validation can lead to authentication bypass and privilege escalation

## Impact
An attacker may forge valid-looking tokens, impersonate users, or escalate privileges without knowing legitimate credentials.

## Fix
- Enforce strict signature verification
- Reject unsigned tokens
- Use secure JWT libraries and configurations
- Validate algorithms and token integrity correctly
