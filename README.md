# Growthify — WP Engine Security Tracker

Password-protected static dashboard tracking WordPress security hardening across
Growthify-managed WP Engine sites. The page in `docs/` is AES-encrypted client-side
with [StatiCrypt](https://github.com/robinmoisson/staticrypt) and served by GitHub
Pages — this repository contains **ciphertext only**.

## Workflow

- Source HTML lives locally in `public-encrypted/` (gitignored — never committed).
- `make encrypt` encrypts it into `docs/` using a password derived from
  `ENCRYPT_SECRET` in the local `.env` (also gitignored).
- `make encrypt-show` prints the derived password without re-encrypting.
- Commit + push `docs/` to publish.

Checklist state (ticks) is stored in the viewer's browser via localStorage.
