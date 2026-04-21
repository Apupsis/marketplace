---
description: Perform a thorough code review of the current diff or specified files, categorizing findings by severity and providing actionable recommendations.
---

# Review Command

Conduct a comprehensive code review covering correctness, security, performance, and maintainability.

## Scope

This command reviews code for:
- Logic errors and incorrect behavior
- Security vulnerabilities (OWASP Top 10, injection, auth flaws)
- Performance anti-patterns and bottlenecks
- Missing or inadequate error handling
- Test coverage gaps and weak test cases
- Naming, readability, and documentation issues
- Dependency and version risks
- Adherence to project conventions

## Execution Flow

1. Read the diff or specified files in full
2. Understand the stated purpose of the change
3. Check logic for correctness and edge case handling
4. Scan for security vulnerabilities
5. Assess performance implications
6. Review error handling and resilience
7. Evaluate test coverage and test quality
8. Check naming, readability, and inline documentation
9. Categorize each finding: Blocker / Major / Minor / Suggestion
10. Write a concise finding for each issue with location and fix
11. Provide an overall verdict: Approve / Request Changes / Needs Discussion

## Constraints

- Use code-quality review and refactoring skills
- Always cite file name and line number for each finding
- Distinguish bugs from style suggestions — prioritize correctly
- Suggest specific fixes, not vague recommendations
- Acknowledge what the code does well
- Note any assumptions made during review
- Keep feedback constructive and actionable
