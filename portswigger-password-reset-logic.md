# PortSwigger Lab - Password Reset Broken Logic

## Vulnerability
Broken password reset logic

## Description
The application’s password reset functionality was flawed, allowing unauthorized password changes due to improper validation in the reset process.

## What I did
- Analyzed the password reset workflow
- Identified weaknesses in how reset requests were handled
- Exploited the logic flaw to reset another user’s password
- Logged in to the account using the new credentials

## Key Learning
- Password reset mechanisms are a critical attack surface
- Logic flaws can allow attackers to take over accounts
- Proper validation and secure token handling are essential

## Impact
An attacker can reset another user’s password and gain full account access, leading to account takeover.

## Fix
- Use secure, unique, and time-limited reset tokens
- Validate ownership before allowing password changes
- Ensure reset workflows cannot be manipulated
