# PortSwigger Lab - Authentication Enumeration

## Vulnerability
Username and password enumeration via different error messages

## What happened
- Application responded differently for valid vs invalid usernames
- Used this to identify a valid username
- Then performed password testing for that user

## Key Learning
- Small differences in responses can reveal sensitive information
- Enumeration is a critical step in attacks

## Fix
- Use generic error messages (same for all cases)
- Avoid revealing whether username exists
