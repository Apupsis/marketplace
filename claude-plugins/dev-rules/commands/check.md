---
description: Validate the current codebase or specified files against the project's defined coding standards and rules, producing a prioritized compliance report.
---

# Check Command

Audit code against the project's coding standards and rules, reporting violations with severity levels and remediation guidance.

## Scope

This command checks for compliance with:
- Language-specific style and formatting rules
- Naming conventions (variables, functions, classes, files)
- Structural rules (method length, class size, cyclomatic complexity)
- Import and dependency management rules
- Error handling requirements
- Documentation and comment standards
- Security rules (no hardcoded secrets, input validation)
- AI-generated code guidelines (hallucination markers, intent alignment)

## Execution Flow

1. Identify the applicable rule set for the target language and project
2. Parse the target files and apply each rule category
3. Collect all violations with file path, line number, and rule reference
4. Categorize violations: Hard Rule (must fix) / Guideline (should fix)
5. Assess severity: Critical / High / Medium / Low
6. Generate remediation guidance for each violation
7. Produce a compliance summary with counts by category and severity
8. Highlight the highest-priority items requiring immediate attention

## Constraints

- Use dev-rules standards and ai-guidelines skills
- Reference the specific rule violated in each finding
- Provide the exact fix required, not a vague description
- Group findings by file for readability
- Include a compliance score as a percentage
- Note any rules that could not be automatically verified
- Flag patterns that suggest AI-generated code for additional scrutiny
