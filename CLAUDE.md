# Working rules for this repository

The person working with Claude here is not a programmer. These rules exist so
that behavior can be checked against them, not just aspired to.

## How to explain things

- Default to plain language, no unexplained jargon.
- If a technical term is genuinely necessary, define it in one line at the
  point it's used. Don't assume prior vocabulary.
- Violation looks like: using a technical term (e.g. "rebase," "dependency,"
  "endpoint") without a one-line definition the first time it appears.

## Ask before doing (stop and check in, then proceed once told to)

Claude must pause and ask before:

1. **Adding any new dependency or library** — even a small, popular,
   "obviously fine" one. No package gets added silently.
2. **Touching files outside what was actually asked about.** If solving the
   stated task seems to require changing an unrelated file, stop and name
   that file before editing it — don't expand scope quietly.
3. **Changing configuration or settings files** — anything that changes how
   the project behaves, builds, or deploys (e.g. `.env` files, CI/workflow
   files, `settings.json`-style config), as opposed to ordinary code/content
   files.
4. **Running anything that costs money or calls a paid API** — including
   API calls that consume credits or cloud commands that spin up billed
   resources.

## Never do without explicit go-ahead in the moment

These are hard stops — a standing "ask first" isn't enough; each instance
needs a real yes:

1. **Force-push or rewrite git history** — `git push --force`,
   `git rebase -i`, amending commits that are already on GitHub, or anything
   else that can permanently destroy history.
2. **Delete files, branches, or data** — any deletion, no matter how small it
   looks, gets a specific yes each time.
3. **Commit or push anything containing secrets or credentials** — API keys,
   passwords, tokens. Check file contents before committing, even when a
   filename looks harmless.

## Committing and pushing

- Claude does not commit or push on its own initiative.
- Work is committed only when explicitly told to commit, and pushed only
  when explicitly told to push — every time, not just the first time.
- A prior approval to commit/push does not carry forward to later, unrelated
  changes.
- Commit messages are a single plain-language summary line in imperative
  mood (e.g. "Add project description to README"), no prefixes like
  "feat:" or "fix:".
