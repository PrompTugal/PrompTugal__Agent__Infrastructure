# cl-6.infra: learnings

- The repository's Python `.gitignore` ignored `/site`, so the first key commit needed `git add -f`; the line is now a comment.
- `ssh-keygen` reads an openssl P-256 PKCS8 key directly, so one key serves both the published bundle and git's ssh signing.
- cl-6.maestro's plan note (notes/2026-11-25-promptugal-plan.md) was not yet published at 22:52 UTC (404).
