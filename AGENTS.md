# AGENTS.md

Instructions for any AI agent working in this repository.

## Purpose

This repo is a shared workspace bridged across multiple AI platforms (Grok, ChatGPT, Gemini, Claude, Copilot). Any agent may read and write here. The repo is the single source of truth for handoffs.

## Rules

1. **Read before writing.** Check STATE.md and HANDOFF.md before starting work so you know what the last agent did and what is in progress.
2. **Update STATE.md** at the end of every session: current status, last-touched-by (platform + model), and next steps.
3. **Append to HANDOFF.md** for anything the next agent needs to know — decisions, blockers, file paths, commands that worked.
4. **Never commit secrets.** No API keys, tokens, passwords, or personal data in repo files. Use environment variables or a secrets manager (1Password / Bitwarden) and reference them by name only.
5. **Nothing destructive without explicit owner confirmation.** No force-pushes, deletions, or revocations unless the owner says so in chat.
6. **Pace API calls.** Respect platform rate limits (GitHub: 5,000 requests/hour authenticated; 80 content-creating requests/minute). On 429, honor Retry-After or sleep until X-RateLimit-Reset, then retry with backoff.
7. **Keep the repo private.** Connected data can flow into prompts, caches, and training-adjacent artifacts on each platform. The repo is the one place you can audit and delete.

## File conventions

- `AGENTS.md` — this file. Standing instructions for all agents.
- `STATE.md` — current status snapshot. Overwrite each session.
- `HANDOFF.md` — append-only session notes for the next agent.
- `SECURITY.md` — token hygiene, 2FA, revocation checklist.

## Platform notes

- **Grok:** native GitHub connector (grok.com/connectors). Can search, read, push, open PRs, manage issues.
- **ChatGPT:** GitHub app / connectors. Read and write repos.
- **Gemini:** two-way GitHub sync in AI Studio; web version is upload-only.
- **Claude:** GitHub via MCP server.
- **Copilot:** built-in GitHub access.
- **Google Drive:** Grok, ChatGPT, Gemini (strongest on Gemini via Workspace).
- **Notion:** Grok, ChatGPT.
- **Linear:** Grok, ChatGPT.

## Security checklist (see SECURITY.md)

- [ ] 2FA enabled on every bridged account (authenticator app or passkey, not SMS)
- [ ] Password manager in use (1Password or Bitwarden) with unique passwords per account
- [ ] OAuth grants reviewed after setup (Settings → Applications → Authorized OAuth Apps)
- [ ] Quarterly token rotation reminder logged in STATE.md
