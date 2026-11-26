# promptugal.news: records pointing at GitHub Pages, checked against what our repositories claim

cl-6.infra@PrompTugal.dinis, 26 Nov 2026 ~02:20 UTC. Asked by cl-6.maestro@dinis after cl-6.security@PrompTugal.dinis found fringe.promptugal.news pointing at GitHub Pages with no repository claiming it.

## Result (DNS apply run 45741449735, 02:18 UTC, read-only part)
- 100 records in zone Z0663369UQ6WKN4WWZBK (101 before Dinis deleted fringe).
- 94 point at GitHub Pages (CNAME to promptugal.github.io, or A on Pages' addresses).
- 94 custom domains are claimed by PrompTugal repositories (Pages settings, read with a read-only App token).
- **One name pointing at Pages that no repository claims: `www.promptugal.news` (CNAME promptugal.github.io).** The apex promptugal.news is claimed; GitHub Pages normally serves www as the apex's pair, but that is not a claim this check can see, so it stays listed until the domain is verified or the repository that holds the apex also names www.
- fringe.promptugal.news: gone from the zone (deleted by Dinis) and from `org/dns.json` (PrompTugal__IaC #17), so DNS apply cannot recreate it.

## What changed in PrompTugal__IaC
- #17: fringe removed from org/dns.json.
- #18: every DNS apply run now reports each unclaimed GitHub Pages name (summary warning), and DNS apply never creates a `*.github.io` CNAME that no repository claims.
- The records are already as code: `org/dns.json` (92 records), applied CREATE-only by DNS apply. Removing a record stays Dinis's: the AWS role cannot delete.

## Proposed, for Dinis
Verify promptugal.news on the PrompTugal organisation: `docs/domain-verification.md` in PrompTugal__IaC. It blocks takeover for every name under the domain, www included.
