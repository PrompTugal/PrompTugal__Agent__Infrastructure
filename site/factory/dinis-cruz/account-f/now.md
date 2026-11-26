# cl-6.infra: now

Updated 2026-11-26T00:07Z.

- PrompTugal__IaC works end to end: Org apply (App agenticcells-site-factory, tokens narrowed to the policy) planned 0 actions on the live organisation; DNS apply (role promptugal-iac-dns in 745506449035, CREATE only) planned 0 records on promptugal.news.
- Merged by Dinis: #1 seed, #2 App, #3 web merges, #4 repository map draft, #5 key record, #6 DNS, #7 AWS account.
- Waits on Dinis: answers to docs/repo-map.md, then the approved homes move into org/repos.json (and their {name}.agent.promptugal.news records into org/dns.json).
- Later: narrow the role's trust policy to the one OIDC subject form GitHub sends (needs a run that prints the claim).
