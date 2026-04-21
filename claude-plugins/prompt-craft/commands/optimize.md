---
description: Analyze an existing prompt and rewrite it for improved accuracy, consistency, and token efficiency without changing its intent.
---

# Optimize Command

Analyze an existing AI prompt and produce an optimized version that achieves the same goal more reliably and efficiently.

## Scope

This command improves existing prompts by addressing:
- Ambiguous or contradictory instructions
- Missing context that causes hallucinations
- Verbose phrasing that wastes tokens
- Weak output format specifications
- Absent or insufficient few-shot examples
- Missing chain-of-thought scaffolding for reasoning tasks
- Inconsistent role definitions

## Execution Flow

1. Parse the existing prompt and identify its objective
2. Run a diagnostic against common failure patterns
3. Measure baseline token count and identify inefficiencies
4. Rewrite ambiguous instructions with precise language
5. Tighten verbose sections without losing meaning
6. Strengthen output format specifications
7. Add or improve few-shot examples if needed
8. Introduce chain-of-thought if the task requires reasoning
9. Compare original and optimized versions side by side
10. Document every change and its rationale

## Constraints

- Preserve the original intent exactly — optimization must not change behavior
- Use prompt-craft skills for improvement patterns
- Quantify token reduction where applicable
- Provide a diff-style summary of changes
- Test the optimized prompt against the same inputs as the original
- Flag any trade-offs (e.g., shorter prompt may reduce accuracy on edge cases)
