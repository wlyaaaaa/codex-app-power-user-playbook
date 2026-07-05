# Codex App Power User Playbook

**Turn Codex App into a long-running engineering agent: tested workflows for skills, plugins, worktrees, browser automation, reviews, automations, and custom rules.**

This is an unofficial, practical playbook for people who want to push Codex App beyond "chat with a coding assistant" and use it as a serious engineering operator.

If you are trying to answer questions like these, this repo is for you:

- How do I make Codex behave like a persistent engineering agent?
- When should I use skills, plugins, MCP, hooks, worktrees, browser automation, or subagents?
- How do I write global `AGENTS.md` rules that Codex can actually follow?
- How do I test Codex App capabilities instead of guessing what works?
- How do I keep powerful local automation useful without accidentally publishing secrets or breaking my machine?

## What You Get

- A public-safe `AGENTS.md` template for global Codex behavior.
- A capability map for Codex App power users.
- A tested Markdown-to-PDF skill example with a self-contained script.
- Practical rules for using skills and plugins as reusable capability packages.
- Safety boundaries for GitHub, browser automation, local files, desktop control, and external side effects.

## Highlights

### Codex App Capability Map

Codex is not just a prompt box. In the App, it can coordinate:

- Worktrees for isolated code changes.
- Code review workflows against a base branch or commit.
- In-app browser checks for local UI work.
- Chrome automation for logged-in browser state.
- Skills for task-specific operating procedures.
- Plugins that bundle skills, scripts, MCP servers, hooks, and app entries.
- Automations for reminders and recurring checks.
- Local environment actions for repeated commands.
- Hooks and rules for deterministic lifecycle behavior.

See [docs/capability-map.md](docs/capability-map.md).

### Public AGENTS Template

Use [templates/AGENTS.public.md](templates/AGENTS.public.md) as a starting point for your own global or project-level Codex rules.

It covers:

- Default collaboration preferences.
- When Codex should ask vs execute.
- When to use worktrees, subagents, browser automation, review, and automations.
- How to treat external side effects.
- How to keep skills and plugins self-contained.

### Skill + Plugin Example

The repo includes a small Markdown-to-PDF example:

- [examples/skills/md-to-pdf/SKILL.md](examples/skills/md-to-pdf/SKILL.md)
- [examples/plugins/md-pdf-toolkit/scripts/build_docs_pdf.py](examples/plugins/md-pdf-toolkit/scripts/build_docs_pdf.py)

The example is intentionally self-contained. It avoids depending on random files from another project directory, handles Windows + Edge headless rendering, and prints to an ASCII temporary PDF path before replacing the final target file.

## Quick Start

1. Copy [templates/AGENTS.public.md](templates/AGENTS.public.md) into your project or global Codex rules.
2. Edit the preferences to match your risk tolerance and workflow.
3. Add one small skill for a task you repeat often.
4. Test it in a fresh Codex thread.
5. When a skill or plugin fails in a real task, update the skill/plugin itself, not just your memory of the fix.

## Important Safety Note

Do not publish your real personal `AGENTS.md` without reviewing it first.

Global agent files often contain:

- Local absolute paths.
- Private service names.
- API endpoints.
- Internal workflows.
- Account names.
- Security assumptions.
- Rules that only make sense on one trusted machine.

For public repos, publish templates and examples, not your private operational manual.

## Repo Structure

```text
.
├── README.md
├── docs/
│   └── capability-map.md
├── templates/
│   └── AGENTS.public.md
└── examples/
    ├── skills/
    │   └── md-to-pdf/
    │       └── SKILL.md
    └── plugins/
        └── md-pdf-toolkit/
            └── scripts/
                └── build_docs_pdf.py
```

## Status

This is a living playbook. It is based on hands-on Codex App testing, but Codex changes quickly. Treat the repo as a starting point, then validate each capability in your own environment.

## Keywords

Codex App, OpenAI Codex, AI coding agent, AGENTS.md, skills, plugins, MCP, worktrees, browser automation, AI engineering workflow, agentic coding.

## License

MIT
