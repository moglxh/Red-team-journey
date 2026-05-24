# PortSwigger Labs - Insecure Deserialization

## Labs Completed
- Modifying serialized objects
- Modifying serialized data types

## Vulnerability
Insecure Deserialization

## Description
The application trusted serialized user-controlled data without proper validation. By modifying serialized values and data types, application logic could be manipulated.

## What I learned
- Understanding serialized object structures
- Modifying serialized parameters safely
- Manipulating data types to alter application behavior
- Identifying trust issues in server-side deserialization

## Key Learning
- Applications should never trust client-controlled serialized data
- Type handling inconsistencies can introduce logic flaws
- Deserialization vulnerabilities may lead to privilege escalation or remote code execution

## Impact
An attacker may manipulate application logic, bypass restrictions, escalate privileges, or potentially achieve code execution depending on the deserialization implementation.

## Fix
- Avoid deserializing untrusted user input
- Validate integrity of serialized data
- Use secure serialization mechanisms
- Enforce strict server-side validation
