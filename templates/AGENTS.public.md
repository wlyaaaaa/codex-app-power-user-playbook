# Global Codex Preferences

Use this file as a public-safe starting point for your own `AGENTS.md`.

Project-level `AGENTS.md` files should override these defaults when they contain more specific instructions.

## Collaboration Style

- Use the user's preferred language by default.
- Keep code, commands, paths, logs, errors, model names, and API field names in English.
- Do not reveal hidden chain-of-thought. Provide concise reasoning summaries, plans, and verification evidence instead.
- Prefer engineering judgment over generic tutorials.
- When information is enough, choose a direction and act.
- When a key variable is missing and guessing would be risky, ask one concise question.

## Execution Rules

- Before large searches, file edits, command execution, or tool use, briefly say what you are about to do.
- Low-risk local actions can proceed without confirmation.
- High-risk or external side-effect actions require explicit intent.

High-risk examples:

- Deleting or overwriting important files.
- Resetting workspaces.
- Changing permissions or security policy.
- Running database migrations.
- Sending messages or emails.
- Publishing posts.
- Committing, pushing, releasing, or creating pull requests.
- Deploying, rolling back, changing production settings, or deleting cloud resources.

## Capability Routing

Before acting, route the task to the right Codex capability.

- Use worktrees for isolated or risky code changes.
- Use review mode for diffs, pull requests, and quality checks.
- Use the in-app browser for local UI preview and DOM/screenshot verification.
- Use Chrome automation when existing browser login state matters.
- Use subagents when there are independent investigation tracks.
- Use automations for reminders, recurring checks, and monitors.
- Use skills for repeated workflows.
- Use plugins when a workflow needs skills plus scripts, MCP, hooks, or other assets.

## Skills And Plugins

- Treat visible skills and installed plugins as available unless testing proves otherwise.
- Do not confuse "available" with "fully verified".
- Record failures and workarounds in the skill or plugin itself.
- Keep personal skills and plugins self-contained.
- Put scripts, templates, and helper assets next to the skill/plugin.
- Avoid depending on random files from unrelated local project folders.

## Durable State Layout

- Keep the app runtime home, such as `~/.codex`, separate from your long-term rule and capability source repo.
- Treat the runtime home as config, installed state, caches, sessions, memories, and diagnostics, not as your main source repo.
- Keep curated global rules, user guides, capability notes, personal skills, and personal plugin source in a stable repo or directory.
- If you back up runtime-home memory, use a separate private repo and a whitelist-only sync.
- Do not mirror auth files, sessions, JSONL logs, SQLite databases, caches, temp directories, or package/plugin caches.
- Preserve richer historical memory backups when the current runtime memory file is smaller.
- Verify scheduled backups with task status, result code, logs, local snapshot presence, and Git remote state.

## Verification

Before claiming completion:

- Run the relevant verification command.
- Read the output.
- Report what passed and what was not tested.

Useful verification:

- Tests.
- Type checks.
- Builds.
- Linters.
- Smoke checks.
- PDF/page render checks.
- Browser screenshots or DOM checks.

## Public Safety

Do not publish private operational rules directly.

Remove or generalize:

- Local absolute paths.
- API tokens and credential file locations.
- Account identifiers.
- Private service names.
- Internal project names.
- Personal automation details.
- Private backup repository names and scheduler task names.

Publish templates and examples, not your full private agent brain.
