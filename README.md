# ParseWorks

ParseWorks is a React + TypeScript + Vite app for reading and annotating texts (including OCR-based PDF workflows), with local storage and export tooling.

## Development

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

## Public release hardening

Before publishing this code to a public repository, run the sanitization workflow:

```bash
bash scripts/prepare_public_release.sh ../ParseWorks-public
```

This script creates a clean copy with:

- Git history removed.
- known sensitive files removed.
- strict `.gitignore` defaults for release artifacts and signing files.
- a lightweight secret scan pass for common credential patterns.

See `SECURITY_PUBLIC_RELEASE.md` for details and manual verification guidance.
