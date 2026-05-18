D# PortSwigger Labs - OS Command Injection

## Labs Completed
- OS command injection, simple case
- Blind OS command injection with time delays
- Blind OS command injection with output redirection

## Vulnerability
OS Command Injection

## Description
The application unsafely incorporated user-controlled input into system commands executed on the server. This allowed arbitrary operating system commands to be injected and executed.

## What I learned
- Direct command execution through vulnerable parameters
- Blind command injection using time-based techniques
- Blind command injection using output redirection
- Importance of understanding server-side execution flow

## Key Learning
- Applications must never directly pass user input into system commands
- Blind vulnerabilities can still be exploited even without direct output
- Attackers can confirm execution using side channels like delays and redirected output

## Impact
An attacker may execute arbitrary commands on the server, potentially leading to remote code execution, data theft, or full server compromise.

## Fix
- Avoid using system commands with user input
- Use safe APIs instead of shell execution
- Properly sanitize and validate input
- Apply least privilege principles
