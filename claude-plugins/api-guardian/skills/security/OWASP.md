# OWASP API Security Top 10

## API1:2023 Broken Object Level Authorization

- Validate user access to specific resources
- Check authorization on every object access
- Use UUIDs instead of sequential IDs
- Implement consistent authorization checks

## API2:2023 Broken Authentication

- Use industry-standard authentication (OAuth2, OpenID)
- Implement proper session management
- Enforce strong password policies
- Use multi-factor authentication for sensitive operations
- Protect against brute force attacks

## API3:2023 Broken Object Property Level Authorization

- Validate which properties users can read/write
- Use allow lists for permitted fields
- Implement field-level authorization
- Avoid mass assignment vulnerabilities

## API4:2023 Unrestricted Resource Consumption

- Implement rate limiting per user/IP
- Set maximum request sizes
- Limit pagination and query results
- Timeout long-running operations
- Monitor resource usage

## API5:2023 Broken Function Level Authorization

- Enforce role-based access control
- Deny by default, allow explicitly
- Check authorization on all endpoints
- Separate admin functions properly

## API6:2023 Unrestricted Access to Sensitive Business Flows

- Identify sensitive workflows (payments, registration)
- Implement additional protections (CAPTCHA, device fingerprinting)
- Monitor for automated abuse
- Rate limit critical operations

## API7:2023 Server Side Request Forgery (SSRF)

- Validate and sanitize URLs
- Use allow lists for permitted domains
- Disable unused URL schemas
- Implement network segmentation

## API8:2023 Security Misconfiguration

- Disable unnecessary features and endpoints
- Keep software and dependencies updated
- Use security headers (HSTS, CSP, X-Frame-Options)
- Configure CORS properly
- Hide version information

## API9:2023 Improper Inventory Management

- Document all API endpoints
- Version APIs properly
- Retire old versions
- Maintain API inventory
- Monitor for shadow APIs

## API10:2023 Unsafe Consumption of APIs

- Validate responses from third-party APIs
- Implement timeouts for external calls
- Use encryption for API communication
- Validate data from all sources
- Implement circuit breakers
