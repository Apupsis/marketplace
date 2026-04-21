---
description: Design a new AI prompt from scratch for a specified task, applying best-practice structure, role definition, and output formatting.
---

# Craft Command

Create a complete, production-ready AI prompt for the specified task using proven prompt engineering patterns.

## Scope

This command produces a structured prompt that includes:
- System role and persona definition
- Task instructions with explicit success criteria
- Relevant context and constraints
- Output format specification
- Few-shot examples (when beneficial)
- Chain-of-thought guidance (when reasoning is required)

## Execution Flow

1. Clarify the task objective and target model
2. Identify the appropriate prompting pattern (zero-shot, few-shot, chain-of-thought, ReAct)
3. Define the system role with clear persona and scope
4. Write task instructions using precise, unambiguous language
5. Specify the output format (JSON, markdown, prose, structured list)
6. Add few-shot examples if the task is complex or format-sensitive
7. Include chain-of-thought scaffolding if multi-step reasoning is needed
8. Add guardrails for common failure modes
9. Validate against a sample input before delivering

## Constraints

- Use prompt-craft prompting skills for structure and patterns
- Apply few-shot skills when examples are warranted
- Keep prompts as concise as possible while meeting objectives
- Include explicit output format instructions
- Document the prompting pattern used and why
- Note any known limitations or failure modes
- Provide at least one example input and expected output
