---
description: Identify refactoring opportunities in the specified code and execute a safe, incremental refactoring plan that preserves existing behavior.
---

# Refactor Command

Analyze code for quality issues and apply targeted refactoring techniques to improve structure, reduce complexity, and eliminate technical debt.

## Scope

This command addresses:
- Duplicated code and copy-paste patterns
- Long methods and oversized classes
- Complex conditional logic (high cyclomatic complexity)
- Poor naming that obscures intent
- Dead code and unused dependencies
- Over-engineered abstractions
- Missing or inadequate error handling
- Outdated patterns replaced by better language idioms

## Execution Flow

1. Analyze the target code and identify code smells
2. Verify test coverage exists — add baseline tests if necessary
3. Prioritize refactoring opportunities by impact and risk
4. Plan a sequence of small, safe transformation steps
5. Execute each step: extract method, rename, simplify conditionals, remove duplication
6. Run tests after every step to confirm behavior is preserved
7. Measure improvement: complexity reduction, line count delta, readability
8. Update related documentation and comments
9. Summarize all changes with before/after comparisons

## Constraints

- Behavior must be identical before and after refactoring
- Never refactor code without passing tests as a safety net
- Use code-quality refactoring and review skills
- Apply one transformation type per step — do not combine multiple changes
- Document the rationale for each refactoring decision
- Flag any cases where refactoring revealed latent bugs
- Provide metrics showing the improvement achieved
