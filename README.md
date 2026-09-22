# kit-claude-code-starter

![license MIT](https://img.shields.io/badge/license-MIT-3da639) ![dependencies none](https://img.shields.io/badge/dependencies-none-3da639) [![download v1.0.0 zip](https://img.shields.io/badge/download-v1.0.0%20zip-1f5f4a)](https://github.com/sdvsignal/kit-claude-code-starter/releases/latest) [![more skills and hooks $29](https://img.shields.io/badge/more%20skills%20and%20hooks-$29-1f5f4a)](https://buy.stripe.com/28E28tbob7HE8Xw4B3f3a0b?client_reference_id=from-gh-badge-starter)

**Claude Code works out of the box, then spends your first week asking permission for `npm test` and
forgetting how your repo builds.** This fixes both. Four plain-text files you copy into any repo:
project memory, a permission allowlist, three skills, and an MCP example.

No secrets, no telemetry, no dependencies. Read the whole thing in five minutes.

If you went looking for a Claude Code setup, a CLAUDE.md example, a `.claude/settings.json` permission
allowlist or an `mcp.json` example — that is what is in here. Copy what fits, ignore the rest.

## Want this done for you?

**[Buy Setup Lite — $29](https://buy.stripe.com/3cI14pcsf6DA8Xw4B3f3a0a?client_reference_id=from-gh-starter)** · one repo, CLAUDE.md + allowlist + one skill, back as a PR in ~24h.

Details: [kit.sdvsignal.com/#setup-lite](https://kit.sdvsignal.com/?utm_source=github&utm_medium=readme&utm_campaign=setup-lite&utm_content=kit-claude-code-starter#setup-lite)

## 60-second start

```bash
git clone https://github.com/sdvsignal/kit-claude-code-starter
cp -r kit-claude-code-starter/{CLAUDE.md,.claude,.mcp.json.example} your-repo/
cd your-repo && claude
```

Then type `/ship-check`. It will run your tests and lint and report PASS/FAIL — or tell you exactly
which command it could not find, which is your cue for the next step.

## The 15 minutes that make it yours

The copy above works immediately. These four edits are what turn it from a template into *your*
setup, and step 3 is the one that actually matters.

| Min | Step |
|---|---|
| 0–2 | Install Claude Code (`npm install -g @anthropic-ai/claude-code`) and run `claude` once in your repo to sign in. |
| 2–5 | Copy `CLAUDE.md`, `.claude/` and `.mcp.json.example` into your repo root. |
| 5–10 | **Edit `CLAUDE.md`**: fill in the four commands (install / dev / test / lint) and the "never do" list. This is the step that matters. |
| 10–12 | Edit `.claude/settings.json` → `permissions.allow` so it matches your real test and lint commands. |
| 12–15 | Run `claude`, then `/ship-check`. It should run your tests and lint and report PASS/FAIL. |

## What's in each file

### `CLAUDE.md`
It's short on purpose. Claude reads it at the start of every session. Put the commands, the layout, and the
things that bite new contributors in it. Leave the essay out.

### `.claude/settings.json`
- **allow**: read-only git, your test/lint commands, and package-manager installs.
- **deny**: `rm -rf` (and `-fr`, `-Rf`, `-r`), force-push (`--force` and `-f`), reading `.env*`. Deny rules match command text, so they catch the usual spellings, not every one. A PreToolUse hook is the stronger guard.
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

## Free here vs. paid

**Everything above is MIT and complete.** Nothing is held back, and there is no paid tier of this repo.

What you are buying, if you ever buy, is the 15 minutes plus the judgement calls — which commands
belong in the allowlist, what goes in the "never do" list, which of your services deserve an MCP
server. That is a **Kit Setup Sprint**, and it comes back as a PR you review.

### Want more of the same thing, today, with nobody involved?

This starter is **3 skills and one formatting hook**. If what you actually want is *more files of
this kind* rather than a service with a turnaround, that is the
**[Skills & Hooks Pack — $29](https://buy.stripe.com/28E28tbob7HE8Xw4B3f3a0b?client_reference_id=from-gh-starter)** — 10 skills and 8 hooks, drop-in
`.claude/`, instant download, no intake and no clock.

Six of those eight hooks **block** rather than warn: a write containing a live credential, a commit
straight onto `main`, `rm -rf` at a root or a bare wildcard, `git clean -fd`, reading a `.env` into
the transcript, and the flags that make a test run report success whatever happens. It ships with
134 offline tests you can run before trusting any of it — 95 over the hooks, and 39 that
prove every skill's frontmatter parses, because a skill that does not parse never loads and
says nothing about it.

Two of its files are [published in full before you pay](https://kit.sdvsignal.com/samples/skills-hooks?utm_source=github&utm_medium=readme&utm_campaign=skills-hooks&utm_content=kit-claude-code-starter),
along with the complete file list and a replay of the hooks refusing real mistakes. Read those two
and if they are not worth $29 to you, the other 24 will not be either.

| | Setup Lite | Setup Sprint | MCP Basic | Build Packet |
|---|---|---|---|---|
| Price | **[$29](https://buy.stripe.com/3cI14pcsf6DA8Xw4B3f3a0a?client_reference_id=from-gh-starter-table)** | **[$99](https://buy.stripe.com/4gM4gBeAn7HE2z80kNf3a01?client_reference_id=from-gh-starter-table)** | **[$199](https://buy.stripe.com/14A4gB9g38LIc9IebDf3a07?client_reference_id=from-gh-starter-table)** | **[$399](https://buy.stripe.com/9B600lcsfaTQb5EebDf3a02?client_reference_id=from-gh-starter-table)** |
| What | A CLAUDE.md, a tool allowlist and one skill, set up for your repo | CLAUDE.md + skills + allowlist + hooks + up to 3 MCP servers + runbook, tuned to your repo | One MCP tool + schema + smoke prompt + enable/disable notes | One custom MCP server (≤5 tools) **or** one Cloudflare Worker (≤3 routes) with tests + README |
| Turnaround | 24 hours, as a PR you review | 48 hours | a few days | 5 business days |

Every price in that row is a live checkout. Nothing there is a subscription and nothing expires.

Shipping an iOS app too? **Preview Pack $149** is one App Store preview video built to Apple's spec from your
screen recordings, plus 5 stills and 2 revision rounds, in 72 hours. Same page.

**→ Scope and order: [kit.sdvsignal.com](https://kit.sdvsignal.com/?utm_source=github&utm_medium=organic&utm_campaign=afm-find&utm_content=gh-readme-kit-claude-code-starter)**

We use AI tools including Claude; a person reviews every deliverable before it ships.
Independent project, not affiliated with Anthropic.

## Questions

Stuck on the `CLAUDE.md` step, or not sure what belongs in the allowlist? Ask in
[Discussions](https://github.com/sdvsignal/kit-claude-code-starter/discussions/1). Real answers, no signup.

## Related

- [kit-plugins](https://github.com/sdvsignal/kit-plugins) — the same skills as installable Claude Code plugins
- [kit-one-tool-mcp](https://github.com/sdvsignal/kit-one-tool-mcp) — a working one-tool MCP server sample, 15 tests, no API key
- [kit-ios-worker-template](https://github.com/sdvsignal/kit-ios-worker-template) — StoreKit 2 verification on a Cloudflare Worker, with failure logging

## License

MIT. Use it, fork it, strip the branding.
