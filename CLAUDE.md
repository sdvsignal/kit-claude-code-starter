# Project: <your-app>

## Commands
- Install: `npm install`
- Dev: `npm run dev`
- Test: `npm test`
- Lint: `npm run lint`
- Typecheck: `npm run typecheck` (delete this line and its allow rule if your repo has none)

## Layout
- `src/`: app code
- `tests/`: tests mirror `src/` paths

## Rules
- Run `npm test` before saying anything is done. A clean build is not proof.
- Small diffs. One concern per commit.
- Match the surrounding code's style; don't reformat files you didn't change.

## Never
- Never read or print `.env*` files or secrets.
- Never force-push or rewrite shared history.
- Never add a dependency without saying why in the commit message.
