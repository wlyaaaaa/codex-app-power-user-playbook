# Codex App Capability Map

This page summarizes the practical Codex App capabilities worth testing and turning into repeatable workflows.

## Core Engineering

### Worktrees

Use worktrees when the main workspace has uncommitted changes or a task could pollute the current branch.

Best for:

- Feature experiments.
- Risky refactors.
- Parallel code paths.
- Review or reproduction branches.

### Review Mode

Use review mode when checking changes against a base branch, pull request, or merge base.

Good review output should:

- Lead with actionable findings.
- Reference files and lines.
- Avoid speculative comments.
- Clearly say when no actionable issues were found.

### Verification Loop

Before claiming success, Codex should run a relevant verification command and report evidence.

Useful checks:

- Tests.
- Type checks.
- Builds.
- Linters.
- Render checks for documents and UI.

## Browser And UI

### In-App Browser

Use for local UI preview and debugging. Prefer `localhost` or `127.0.0.1` over `file://`.

Useful for:

- DOM inspection.
- Screenshot verification.
- CSS and responsive layout checks.
- Local web app smoke tests.

### Chrome Automation

Use when a task depends on the user's existing Chrome login state.

Useful for:

- Account dashboards.
- Admin panels.
- Personal workspaces.
- Browser-only workflows.

Rules:

- Do not reveal private page details unless requested.
- Ask or require explicit intent before posting, deleting, paying, publishing, or changing account settings.

## Skills

Skills are reusable operating procedures. A good skill says when to use it, how to execute the workflow, what to verify, and what traps to avoid.

Use skills for:

- Repeated document workflows.
- Debugging playbooks.
- Local API workflows.
- Project-specific release steps.
- Personal formatting or review preferences.

Best practice:

- Keep skills self-contained.
- Put reusable scripts next to the skill or plugin.
- Update the skill after real failures.

## Plugins

Plugins bundle capabilities together. A plugin can contain skills, scripts, hooks, MCP servers, and app entries.

Use plugins when a capability has multiple parts:

- Skill instructions.
- Helper scripts.
- Templates.
- MCP integration.
- Hook behavior.

Best practice:

- Keep plugin source in a stable local or repo path.
- Avoid depending on scripts from unrelated projects.
- Treat plugin installation, current-thread visibility, and new-thread visibility as separate states.

## Automations

Use automations for reminders, recurring checks, monitors, and follow-ups.

Before creating one, define:

- Task.
- Frequency.
- Stop condition.
- Target thread or project.
- Whether it can write files or affect external systems.

## Hooks And Rules

Hooks add deterministic behavior to Codex lifecycle events. Rules control command permissions.

Use them carefully:

- Keep hooks small and predictable.
- Prefer read-only hooks first.
- Do not hide dangerous behavior behind automation.
- Document every hook and rule.

## Public Repository Safety

Before publishing Codex configuration:

- Remove real API paths, tokens, account identifiers, and private workflows.
- Replace machine-specific paths with placeholders.
- Publish templates, not raw personal files.
- Check git history if the repository was already public.
