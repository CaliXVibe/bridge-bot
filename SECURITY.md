# SECURITY.md

Token hygiene, 2FA, and revocation for this bridged workspace.

## Passwords

Use a password manager — **1Password** (recommended) or **Bitwarden** (open source). Every bridged account gets a unique, strong password stored in the vault. Never reuse passwords across platforms.

## 2FA

- Enable on every bridged account.
- Prefer authenticator apps or passkeys. Avoid SMS (GitHub is deprecating SMS for sensitive actions).
- Store TOTP backup codes in the password manager. 1Password can store and autofill TOTP codes.
- **Never read a live 2FA code aloud in chat.** Codes stay in the authenticator app.

## OAuth scope awareness

The GitHub `repo` scope is coarse: full read-write on every repo the user can touch, not just this one. After connecting, review grants at Settings → Applications → Authorized OAuth Apps and revoke anything unrecognized.

## Revocation paths

- GitHub: Settings → Applications → Authorized OAuth Apps / Installed GitHub Apps
- ChatGPT: Settings → Apps & connectors
- Each platform has an equivalent — find it during setup and note it here.

## Rotation

Quarterly: review and rotate all connected tokens. Log the date in STATE.md. Tokens persist until manually revoked, so a breach of one platform exposes standing access to everything else.

## Data residency

Connected data can flow into prompts, caches, summaries, and training-adjacent artifacts, sometimes via downstream subprocessors. Mitigations: keep this repo private, put no secrets or personal data in repo files, prefer connectors with documented retention policies, and audit what each platform has indexed.
