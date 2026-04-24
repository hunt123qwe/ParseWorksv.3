# Public Release Security Checklist

This project previously contained private signing credential details in a local text file. That file has been removed and should not be reintroduced.

## Required steps before publishing

1. Create a clean release copy:

   ```bash
   bash scripts/prepare_public_release.sh ../ParseWorks-public
   ```

2. Review the generated output for secret-scan warnings.
3. Verify no private certificates, keystores, `.env` files, or signing files are present.
4. Rotate any credential that may have been previously committed.

## Android signing guidance

- Keep real `android/signing.properties` local only.
- Use `android/signing.properties.template` as the only tracked reference.
- Keep keystore files out of the repository.

## Recommended CI guardrails

- Add a secret scanner in CI (e.g., gitleaks or trufflehog).
- Block commits containing high-risk patterns (`BEGIN PRIVATE KEY`, cloud provider keys, GitHub tokens).
- Enforce branch protection on your new public repository.
