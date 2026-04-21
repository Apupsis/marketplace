---
description: Perform comprehensive security audit of API implementation including authentication, authorization, and OWASP Top 10 vulnerabilities.
---

# Audit Command

Conduct a thorough security audit of API implementation to identify vulnerabilities and recommend mitigations.

## Scope

This command performs security analysis covering:
- Authentication mechanisms (OAuth, JWT, API keys)
- Authorization and access control logic
- Input validation and sanitization
- Injection vulnerabilities (SQL, NoSQL, command)
- Sensitive data exposure and leakage
- Rate limiting and DoS protection
- Security headers and CORS configuration
- Dependency vulnerabilities

## Execution Flow

1. Review API specification and implementation
2. Analyze authentication and session management
3. Check authorization logic and access controls
4. Test input validation and sanitization
5. Scan for injection vulnerabilities
6. Review error handling and information disclosure
7. Check rate limiting and quota enforcement
8. Verify encryption for sensitive data
9. Document findings with severity levels
10. Recommend specific mitigations with examples

## Constraints

- Use api-guardian security skills for analysis
- Follow OWASP Top 10 methodology
- Provide severity ratings (Critical, High, Medium, Low)
- Include proof of concept for findings
- Recommend practical mitigations
- Consider both design and implementation issues
- Document assumptions and scope limitations
- Prioritize findings by risk and impact
