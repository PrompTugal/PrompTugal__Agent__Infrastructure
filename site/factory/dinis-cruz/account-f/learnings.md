# cl-6.infra: learnings

- The repository's Python `.gitignore` ignored `/site`, so the first key commit needed `git add -f`; the line is now a comment.
- `ssh-keygen` reads an openssl P-256 PKCS8 key directly, so one key serves both the published bundle and git's ssh signing.
- cl-6.maestro's plan note (notes/2026-11-25-promptugal-plan.md) was not yet published at 22:52 UTC (404).
- The same Python `.gitignore` in PrompTugal__IaC ignored `build/`; the first seed commit went without the scripts and a second commit added them.
- The signature check skips the commit that adds it and everything older, so the seed's two commits are reviewed by Dinis rather than checked by CI.
- `set -e` does not stop on a failing command in the middle of an `&&` chain: a leak-scan failure let a commit through. Run checks as separate lines before committing.
- `--force-with-lease` is refused on a branch with no remote-tracking ref in a shallow clone; pushing the correction to a new branch avoids rewriting anything.
- A two-call change (clear then set a Pages domain) must always run its second call: GitHub returned HTTP 500 on a clear and the run stopped with the domain possibly unset (a takeover window). Fixed in PrompTugal__IaC #24.
- Report a run as done only after reading its result: I told Dinis the nudge had run on all 77 sites before the run had finished, and it had failed part-way.
- GitHub refuses push rulesets (file_path_restriction) on public repositories: HTTP 422 "Source public repos cannot have push rules" (rules probe run 45743552530).
- A workflow with both push and dispatch triggers runs on every merge too: Org apply re-nudged all 25 stuck certificates on each merge to org/, so seven cycles hit one site in a day, each a takeover window and a push race. A repeating repair must be opt-in and rate-limited (PrompTugal__IaC #28), and a repair that does not work (bad_authz stays) should stop, not repeat.
- Write a time only from date -u: I stamped a message 16:14 UTC when the clock read 16:09.
- Certificates seen from this sandbox are re-signed by its egress proxy (issuer "Anthropic Egress Gateway"); a site's real certificate state comes only from GitHub's Pages API.
- `cmd | tail -1 && next` lets a failing cmd through (the pipe's status is tail's): a commit with two failing tests reached a branch (IaC #29's first commit). Use set -o pipefail before such chains.
- test/run.mjs prints its summary and exit code at a fixed line: a test appended after it runs uncounted and cannot fail the run. Append tests above the summary (found 27 Nov while writing IaC #35).
- A rollout step that names an owner in docs is not owned until that owner has agreed: #25's "cl-6.conductor confirms each release.sh" was never picked up, and every section turned out not ready. Gate a rollout on a check per section instead.
