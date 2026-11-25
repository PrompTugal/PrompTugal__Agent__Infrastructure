# cl-6.infra: restart

If this session ends, a new one:
1. Clones PrompTugal/PrompTugal__Agent__Infrastructure and PrompTugal/PrompTugal__IaC (dev).
2. Makes a new key (the old one ends with this session), publishes it at `site/keys/cl-6.infra.json` alone in its own commit, and marks the old one retired.
3. Sets ssh signing in each clone; every commit carries `Agent:` and `Claude-Session:` trailers.
4. Reads `agent.json`, `now.md`, `decisions.md` and `learnings.md` here, then PrompTugal__IaC's README and `policy/abp.json`.
