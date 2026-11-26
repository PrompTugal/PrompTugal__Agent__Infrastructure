# cl-6.infra: Dinis's decisions

## 2026-11-25: dev is every repository's default branch
Dinis's words, relayed by cl-6.maestro@dinis: "please make note to the Infa agent that all repos should have a default dev branch". Confirmed by Dinis in this session (~22:51 UTC): "yes".
Rule in PrompTugal__IaC: every repository in `org/repos.json` has `dev` as its default branch, and Org apply creates `dev` and sets it. A repository whose default would change is listed in a pull request for Dinis before any apply.
Also recorded by cl-6.maestro: SovereignWebsite/Site__Agent__Maestro__Claude__6, `site/factory/dinis-cruz/account-f/decisions/2026-11-25-dev-default-branch.md`.

## 2026-11-25: PrompTugal__IaC attached
Dinis, this session: "yes let's set this up on PrompTugal so that you have access to both AWS and GiHub"; "you need to add https://github.com/PrompTugal/PrompTugal__IaC to this session". The access is CI's: the GitHub App and the AWS role are held by PrompTugal__IaC's apply environment, never by this agent.

## 2026-11-26: one agent per section; places next
Dinis, this session (~00:20 UTC): "one agent per section, because we need to keep it nice and separate"; "I actually even think that you should have an agent per locality, so we track everything that happens there. We just need to figure out what we call it"; "forget about Storm Charles for now, because we need to refactor everything out of it"; "Forget about the apps for here"; the News website split: "start moving the stuff into each agent"; each agent's site is {name}.agent.promptugal.news.
Done as PrompTugal__IaC pull request #9 (Conductor and 14 section homes). Place agents: name to agree.

## 2026-11-26: place agents
Dinis, this session (~00:25 UTC): "PrompTugal__Agent__Place__"; "can you [make] one for all places [that] we current support (I don't think we can use Loulé, it needs to be PrompTugal__Agent__Place__Loule right?)".
Done as PrompTugal__IaC pull request #10: 36 homes, from PrompTugal__News__Website data/by-place/places.json, names in plain ASCII.

## 2026-11-26: cl-6.infra merges pull requests that create
Dinis, this session (~00:23 UTC): "can you merge those PRs? It's fine. I trust you. And that's part of this. You're the only one who can make these changes anyway" (PrompTugal__IaC #9, #10, #11, merged by cl-6.infra). Then: "This also covers future PRs to create stuff, which basically, actually, when if in doubt, can you call the decisions agent, and that should be able to answer for you, because the agent has a workflow to figure out agents, and that signs it for you as that agent."
Rule from here: cl-6.infra merges its own PrompTugal__IaC pull requests that create or configure (repositories, dev branches, settings, CREATE-only DNS records, docs) once Checks pass. In doubt, it asks the decisions agent and acts on the record that agent signs. Still Dinis's unless such a signed record covers it: widening the GitHub App's or an AWS role's privileges, money, deleting anything, main.

## 2026-11-26: decisions agent; sites
Dinis, this session (~00:35 UTC): "use SWS's decisions agent, and go ahead with the sites"; "you should already have permission" (Pages on the App). The decisions agent is decisions.b@SovereignWebsite.dinis (SovereignWebsite__IaC policy/abp.json: session https://claude.ai/code/session_01Kw9UwEVSYcMDgNqrPVfCtZ, records in SovereignWebsite__IaC decisions/). Sites: PrompTugal__IaC #12 (Pages and custom domains for the 51 homes), then their DNS.
Domain check, 00:34 UTC: promptugal.news and its sections resolve to GitHub Pages and are live; no _github-pages-challenge TXT record was found for PrompTugal, so the domain is not verified for the organisation on GitHub.
