---
description: Define or update the coding rules and standards for the current project, generating a structured rules document with tooling configuration.
---

# Define Command

Create or update the project's coding standards and rules framework, producing documentation and tooling configuration that enforces the rules automatically.

## Scope

This command produces:
- A structured rules document covering all applicable categories
- Rationale for each rule explaining the why
- Severity levels and exception procedures
- Tooling configuration (linter rules, formatter settings, pre-commit hooks)
- AI-specific guidelines for teams using code generation
- Onboarding documentation for new contributors

## Execution Flow

1. Assess the project context: language, framework, team size, maturity
2. Survey existing rules (existing linter config, style guides, CLAUDE.md)
3. Identify gaps between current state and best practices
4. Propose rules in each category with rationale
5. Define severity levels and exception handling procedures
6. Generate tooling configuration for automated enforcement
7. Write AI usage guidelines specific to the project
8. Produce the final rules document in the project's documentation format
9. Create a pre-commit hook configuration to enforce rules at commit time

## Constraints

- Use dev-rules standards and ai-guidelines skills
- Every rule must have a clear, documented rationale
- Rules must be automatable or clearly marked as manual guidelines
- Start from established industry standards — extend, do not reinvent
- Include a phased rollout plan if many rules are new
- Provide a migration guide for bringing existing code into compliance
- Define a review cadence for keeping rules current
