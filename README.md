# bridge-bot

Bridge Bot — scaffold a shared GitHub workspace so Grok, ChatGPT, Gemini, Claude, and Copilot can hand work off to each other. AGENTS.md, STATE.md, HANDOFF.md, and SETUP.md templates included.

## Quick start

1. Fork this repo (or let Bridge Bot scaffold a fresh one).
2. Connect your GitHub at grok.com/connectors — one OAuth tap.
3. Tell Bridge Bot: "set up my bridge." It walks you through connectors, scaffold, and verification.
4. Verify: ask it to push a test file and confirm another connected AI can read it.

## What's in the repo

- **SETUP.md** — the full bridge instructions. Any AI can read this and run the setup. This is what makes the bot disposable: delete it, and the knowledge survives in the repo.
- **AGENTS.md** — standing rules every AI reads before working.
- **STATE.md** — status snapshot: connectors, token rotation, rate limits, last verification.
- **HANDOFF.md** — append-only session notes for cross-AI continuity.
- **SECURITY.md** — token hygiene, 2FA, revocation, rotation, data residency.

## Update checks

Every session, the bot reads the version line in SETUP.md and compares it to this canonical repo. If a newer template is available, it tells you — never auto-applies. Updates are opt-in so forks stay stable.

## Security

- Private repo recommended — the single point you can audit and delete.
- No secrets in repo files; references to a vault only (1Password recommended).
- Review OAuth grants after connecting; the `repo` scope is full read-write.
- Quarterly token rotation, logged in STATE.md.
- 2FA via authenticator app or passkey; backup codes in the vault, never in chat.

## License

MIT — see LICENSE.
