# kit-claude-code-starter

A small, opinionated Claude Code setup you can drop into any repo in about 15 minutes. It's what a
**Kit Setup Sprint** delivers, tuned to your stack.

**Want it done for your repo?** Fixed-price setup on the [Kit page](https://kit-sdvsignal.pages.dev):
**Setup Sprint $99** (48h) · **Build Packet $399** (custom MCP or Worker, 5 business days).

- `CLAUDE.md`: project memory. Tells Claude how your repo builds, tests and ships.
- `.claude/settings.json`: a permission allowlist (fewer prompts, nothing destructive) and two hooks.
- `.claude/skills/`: three skills. `ship-check` is a pre-merge gate, `new-feature` is plan → build → test, and `explain-diff` gives a plain-English review.
- `.mcp.json.example`: how to wire an MCP server, with no secrets in the repo.

No secrets and no telemetry live here. Everything is plain text you can read in five minutes.

## 15-minute setup

| Min | Step |
|---|---|
| 0–2 | Install Claude Code (`npm install -g @anthropic-ai/claude-code`) and run `claude` once in your repo to sign in. |
| 2–5 | Copy `CLAUDE.md`, `.claude/` and `.mcp.json.example` into your repo root. |
| 5–10 | Edit `CLAUDE.md`: fill in the four commands (install / dev / test / lint) and the "never do" list. This is the step that matters. |
| 10–12 | Edit `.claude/settings.json` → `permissions.allow` so it matches your real test and lint commands. |
| 12–15 | Run `claude`, then type `/ship-check`. It should run your tests and lint and report PASS/FAIL. |

## What's in each file

### `CLAUDE.md`
It's short on purpose. Claude reads it at the start of every session. Put the commands, the layout, and the
things that bite new contributors in it. Leave the essay out.

### `.claude/settings.json`
- **allow**: read-only git, your test/lint commands, and package-manager installs.
- **deny**: `rm -rf`, force-push, reading `.env*`.
- **hooks**:
  - `PostToolUse` on `Edit|Write` runs the formatter on the file that changed (`.claude/hooks/format.sh`).
  - `Stop` prints a one-line reminder to run `/ship-check` before you commit.

### Skills
| Skill | Use it when |
|---|---|
| `ship-check` | Before a commit or PR. It runs tests + lint + type check and lists anything it couldn't run. |
| `new-feature` | For a feature bigger than one file. It writes a 5-line plan first, then builds, then tests. |
| `explain-diff` | When you want a second read of `git diff` in plain English, with the risky lines flagged. |

### MCP
Copy `.mcp.json.example` to `.mcp.json` and set the env var it names in your shell (not in the file).
Keep `.mcp.json` out of git if it ever holds anything private.

## Need more than this?

| | Setup Sprint | Build Packet |
|---|---|---|
| Price | **$99** | **$399** |
| What | CLAUDE.md + skills + allowlist + hooks + up to 3 MCP servers + runbook, tuned to your repo | One custom MCP server (≤5 tools) **or** one Cloudflare Worker (≤3 routes) with tests + README |
| Turnaround | 48 hours | 5 business days |

Order / scope: [kit-sdvsignal.pages.dev](https://kit-sdvsignal.pages.dev)

We use AI tools including Claude; a person reviews every deliverable before it ships.

## License

MIT. Use it, fork it, strip the branding.
