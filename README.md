# Claude Code Private Marketplace Demo

> A teaching project that shows how to build a private plugin marketplace for Claude Code. Contains two example plugins with agents, commands, and skills -- everything you need to understand the plugin architecture and start building your own.

## What This Demo Shows

If you have been looking at Claude Code plugins and wondering "how do I actually structure a private marketplace for my team?" -- this is your reference. The repository demonstrates:

- How to create a **marketplace manifest** (`marketplace.json`) that lists and distributes plugins
- How to structure **plugins** with agents, commands, and skills
- How plugins, project config (`CLAUDE.md`), and settings work together to form the full Claude Code experience

This is a demo. The plugins here are illustrative -- they show the correct file structure and conventions, not production-ready tooling. Use this as a starting point, then refer to the official docs linked below for the full specification.

## Project Structure

```
demo-claude-marketplace/
├── .claude-plugin/
│   └── marketplace.json          # Marketplace manifest -- lists all plugins
├── claude-plugins/
│   ├── data-toolkit/
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json       # Plugin metadata (name, description, version)
│   │   ├── agents/               # Subagent definitions (data-engineer, pipeline-architect)
│   │   ├── commands/             # Slash commands (ingest, transform)
│   │   └── skills/               # Skills organized by domain (sql/, etl/)
│   ├── api-guardian/
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── agents/               # Subagent definitions (security-auditor, api-reviewer)
│   │   ├── commands/             # Slash commands (audit, scan)
│   │   └── skills/               # Skills organized by domain (openapi/, security/)
│   ├── prompt-craft/
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── agents/               # Subagent definitions (prompt-engineer, prompt-evaluator)
│   │   ├── commands/             # Slash commands (craft, optimize)
│   │   └── skills/               # Skills organized by domain (prompting/, few-shot/)
│   ├── code-quality/
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── agents/               # Subagent definitions (code-reviewer, refactor-guide)
│   │   ├── commands/             # Slash commands (review, refactor)
│   │   └── skills/               # Skills organized by domain (review/, refactoring/)
│   └── dev-rules/
│       ├── .claude-plugin/
│       │   └── plugin.json
│       ├── agents/               # Subagent definitions (rules-enforcer, standards-advisor)
│       ├── commands/             # Slash commands (check, define)
│       └── skills/               # Skills organized by domain (standards/, ai-guidelines/)
├── CLAUDE.md                     # Project-level memory and conventions
└── README.md
```

## How Plugin Marketplaces Work

A marketplace is a Git repository with a `.claude-plugin/marketplace.json` at its root. This manifest declares the marketplace name, owner, and lists all available plugins with their relative source paths.

Here is the manifest from this demo:

```json
{
  "name": "demo-marketplace",
  "owner": {
    "name": "Demo Author",
    "email": "demo@example.com"
  },
  "plugins": [
    {
      "name": "data-toolkit",
      "source": "./claude-plugins/data-toolkit",
      "description": "Adds data engineering agents, commands, and skills for ETL pipeline development."
    },
    {
      "name": "api-guardian",
      "source": "./claude-plugins/api-guardian",
      "description": "Adds API security auditing agents, commands, and skills for governance and OWASP compliance."
    },
    {
      "name": "prompt-craft",
      "source": "./claude-plugins/prompt-craft",
      "description": "Adds AI prompt engineering agents, commands, and skills for designing, optimizing, and evaluating prompts."
    },
    {
      "name": "code-quality",
      "source": "./claude-plugins/code-quality",
      "description": "Adds code review and refactoring agents, commands, and skills for maintaining high code quality standards."
    },
    {
      "name": "dev-rules",
      "source": "./claude-plugins/dev-rules",
      "description": "Adds development rules, coding standards, and AI behavior guidelines agents, commands, and skills."
    }
  ]
}
```

Users add the marketplace and install plugins like this:

```shell
# Add this marketplace (from a Git repo URL or local path)
/plugin marketplace add ./path/to/demo-claude-marketplace

# Install a specific plugin
/plugin install data-toolkit@demo-marketplace
```

For private repositories, Claude Code uses your existing git credential helpers. If `git clone` works in your terminal, it works in Claude Code.

## What Plugins Provide

Each plugin is a directory with `.claude-plugin/plugin.json` at its root, plus any combination of these components:

| Component | Location | Purpose |
|-----------|----------|---------|
| **Agents** | `agents/*.md` | Specialized subagents with custom system prompts, tool access, and permissions. Appear in `/agents`. |
| **Commands** | `commands/*.md` | Slash commands invokable with `/plugin-name:command`. |
| **Skills** | `skills/<name>/SKILL.md` | Reusable expertise modules Claude loads automatically based on task context. Can include supporting files. |
| **MCP Servers** | `.mcp.json` | Model Context Protocol server definitions for external tool integrations. |
| **Hooks** | `hooks/hooks.json` | Event handlers that fire on lifecycle events (PostToolUse, PreToolUse, etc.). |
| **LSP Servers** | `.lsp.json` | Language Server Protocol configs for code intelligence. |

> **Note:** MCP server definitions should live within plugins (via `.mcp.json` or inline in `plugin.json`) when the capability is meant to be reusable across projects. This keeps the MCP configuration bundled with the plugin and distributed through the marketplace automatically.

## Included Plugins

### data-toolkit

Data engineering capabilities for ETL pipeline development and analytics workflows.

- **Agents:** `data-engineer` and `pipeline-architect` -- specialized subagents for data infrastructure tasks
- **Commands:** `/data-toolkit:ingest` and `/data-toolkit:transform` -- slash commands for data operations
- **Skills:** `sql/` and `etl/` -- domain expertise Claude applies automatically when working on data tasks

### api-guardian

API security and governance tooling for auditing, validation, and standards enforcement.

- **Agents:** `security-auditor` and `api-reviewer` -- subagents for security analysis and API design review
- **Commands:** `/api-guardian:audit` and `/api-guardian:scan` -- slash commands for security operations
- **Skills:** `openapi/` and `security/` -- domain expertise for OpenAPI validation and OWASP compliance

### prompt-craft

AI prompt engineering tooling for designing, optimizing, and evaluating prompts.

- **Agents:** `prompt-engineer` and `prompt-evaluator` -- subagents for prompt design and quality assessment
- **Commands:** `/prompt-craft:craft` and `/prompt-craft:optimize` -- slash commands for creating and improving prompts
- **Skills:** `prompting/` and `few-shot/` -- domain expertise for prompt patterns and example selection

### code-quality

Code review and refactoring tooling for maintaining high quality standards across the codebase.

- **Agents:** `code-reviewer` and `refactor-guide` -- subagents for review and safe refactoring
- **Commands:** `/code-quality:review` and `/code-quality:refactor` -- slash commands for code review and refactoring
- **Skills:** `review/` and `refactoring/` -- domain expertise for code analysis and transformation techniques

### dev-rules

Development rules and coding standards tooling for defining, enforcing, and evolving team guidelines including AI usage policies.

- **Agents:** `rules-enforcer` and `standards-advisor` -- subagents for compliance checking and standards design
- **Commands:** `/dev-rules:check` and `/dev-rules:define` -- slash commands for validating and creating coding rules
- **Skills:** `standards/` and `ai-guidelines/` -- domain expertise for coding standards and responsible AI usage policies

## Plugins vs. Project Configuration

Claude Code has two layers that work together. Understanding which concerns belong where is key to a clean setup.

### Plugins handle reusable capabilities

Plugins package agents, commands, skills, MCP servers, and hooks that are **shared across projects and teams**. They are versioned, distributed through marketplaces, and namespaced to avoid conflicts. Use plugins when the functionality is not specific to a single codebase.

### Project config handles domain context

Project-level configuration handles concerns **specific to this codebase**:

- **`CLAUDE.md`** -- project memory: architecture decisions, coding conventions, team guidelines. Claude loads this at the start of every session.
- **`.claude/settings.json`** -- permission rules, environment variables, hooks scoped to this project. This file is committed to git and shared with the team.
- **`.claude/settings.local.json`** -- personal overrides that stay on your machine (gitignored).
- **Hooks** -- lifecycle automation (format on save, block protected files, notifications) that enforces project-specific rules.

The split is straightforward: plugins are for reusable capabilities you distribute, project config is for the domain context and conventions that make this specific codebase work. A plugin might provide a `security-auditor` agent, while your `CLAUDE.md` explains your project's specific authentication architecture so that agent has the right context.

## Getting Started

### Prerequisites

- Claude Code version 1.0.33 or later (`claude --version`)
- Git access to this repository (or a local clone)

### Test locally

```bash
# Clone the repository
git clone <repo-url> demo-claude-marketplace
cd demo-claude-marketplace

# Launch Claude Code with all plugins loaded locally
claude --plugin-dir ./claude-plugins/data-toolkit \
       --plugin-dir ./claude-plugins/api-guardian \
       --plugin-dir ./claude-plugins/prompt-craft \
       --plugin-dir ./claude-plugins/code-quality \
       --plugin-dir ./claude-plugins/dev-rules
```

### Use as a marketplace

```bash
# Add this repo as a marketplace source
# (within Claude Code)
/plugin marketplace add ./demo-claude-marketplace

# Install a plugin
/plugin install data-toolkit@demo-marketplace

# Validate the marketplace structure
claude plugin validate .
```

### Build your own

1. Create your plugin directory with `.claude-plugin/plugin.json`
2. Add `agents/`, `commands/`, and `skills/` directories as needed
3. Define MCP servers in `.mcp.json` if your plugin integrates external tools
4. Create a marketplace manifest at `.claude-plugin/marketplace.json` in a parent repository
5. Host on GitHub, GitLab, or any git host -- users add it with `/plugin marketplace add`

> **Tip:** Start with standalone configuration in `.claude/` for quick iteration, then convert to a plugin when you are ready to share. The docs cover the migration process in detail.

## References

- [Plugins -- Creating Claude Code plugins](https://code.claude.com/docs/en/plugins)
- [Plugins Reference -- Complete technical specifications](https://code.claude.com/docs/en/plugins-reference)
- [Plugin Marketplaces -- Creating and distributing marketplaces](https://code.claude.com/docs/en/plugin-marketplaces)
- [Skills -- Extending Claude with reusable expertise](https://code.claude.com/docs/en/skills)
- [Subagents -- Custom AI agents for task delegation](https://code.claude.com/docs/en/sub-agents)
- [Hooks -- Lifecycle event automation](https://code.claude.com/docs/en/hooks-guide)
- [MCP -- Connecting Claude Code to external tools](https://code.claude.com/docs/en/mcp)
- [Settings -- Configuration scopes and settings files](https://code.claude.com/docs/en/settings)
