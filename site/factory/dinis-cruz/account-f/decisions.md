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
