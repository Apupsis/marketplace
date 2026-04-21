---
description: Scan OpenAPI specification for design issues, security gaps, and compliance with REST best practices.
---

# Scan Command

Analyze OpenAPI specification for design quality, completeness, and adherence to best practices.

## Scope

This command reviews OpenAPI specs for:
- REST compliance (resource naming, HTTP methods)
- Schema completeness and correctness
- Security definitions and requirements
- Error response documentation
- Request/response examples
- Versioning strategy
- Pagination and filtering patterns
- Deprecation notices

## Execution Flow

1. Load and validate OpenAPI specification
2. Check resource naming and URL structure
3. Verify HTTP method usage and status codes
4. Review request/response schemas
5. Validate security definitions
6. Check error response documentation
7. Verify examples and descriptions
8. Assess versioning and deprecation
9. Generate report with findings
10. Provide actionable recommendations

## Constraints

- Use api-guardian openapi skill for validation
- Check against OpenAPI 3.x standards
- Validate schema definitions are complete
- Ensure security schemes are defined
- Verify all endpoints have descriptions
- Check for consistent error handling
- Review naming conventions
- Suggest improvements with examples
