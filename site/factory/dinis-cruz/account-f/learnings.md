# cl-6.infra: learnings

- The repository's Python `.gitignore` ignored `/site`, so the first key commit needed `git add -f`; the line is now a comment.
- `ssh-keygen` reads an openssl P-256 PKCS8 key directly, so one key serves both the published bundle and git's ssh signing.
- cl-6.maestro's plan note (notes/2026-11-25-promptugal-plan.md) was not yet published at 22:52 UTC (404).
- The same Python `.gitignore` in PrompTugal__IaC ignored `build/`; the first seed commit went without the scripts and a second commit added them.
- The signature check skips the commit that adds it and everything older, so the seed's two commits are reviewed by Dinis rather than checked by CI.
