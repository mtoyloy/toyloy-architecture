# Claude Code AI Team

How I run a small AI team in Claude Code. Each agent has one job, its own tools, and a clear limit on what it can do without me.

I am Michelle (Shelly) Toyloy. I use this setup to run projects the way I would run a small delivery team: assign the work, keep the checkers separate from the builders, and approve anything that leaves the building.

## What this is
- A set of agent and skill files written in plain markdown. Claude Code loads them from a project folder.
- A working example, not a product. Connector IDs, account details, and private context are removed.
- The example project is Aisle, my unpublished wedding bouquet pricing prototype. It is not a launched product.

## How the team works
- One job per agent. Each has a role, a short list of tools, and a "never" list.
- Builders and checkers are separate:
  - Maggie (front end) and Bruno (back end) build.
  - Quinn tests what they built and logs bugs. Quinn never fixes them.
  - The security auditor reviews access rules, keys, and personal data. It reports and never fixes.
  - A fixer cannot grade its own work, so the review stays honest.
- A person approves before anything goes out:
  - Stacy drafts email and proposes calendar changes. She never sends or books.
  - Maggie and Bruno write the build prompt first and wait. They send only after I approve the exact text.
  - Fred tells me what he will change in his own files, backs the file up, and logs it. Database changes go to the main session as a proposed prompt.
  - The researcher uses public sources only. It does not sign up, log in, or contact anyone.
- Every agent reports sources, says how sure it is, and says what it could not check.
- Nothing is deleted. Agents add new files and keep a trail.

## Which limits are enforced and which are written
- Enforced by the tool list:
  - Stacy has email draft tools and no send tool.
  - Quinn and the security auditor have no tool to send prompts to the build platform.
  - The researcher, legal advisor, and marketing writer have no edit or send tools.
  - Database query tools are read only.
- Written into the instructions only:
  - The approval step for Maggie and Bruno. They have a send tool, and the rule says to use it only after approval.
  - Fred's backup-before-edit habit.
- I review each run for the second group. A rule in a prompt is not a lock.

## Roster

| Agent | Role | Reviews or builds | Needs my approval for |
|---|---|---|---|
| [Stacy](agents/stacy.md) | Executive assistant: to-do board, inbox, calendar, travel, meeting prep | Neither | Sending, scheduling, booking, sharing |
| [Fred](agents/fred.md) | Data analyst: datasets, cleaning, analysis, A/B results | Reviews data | Large edits, formula changes, database changes |
| [Maggie](agents/maggie.md) | Front end: design brief to build prompt, build review | Builds | Every prompt sent to the build platform |
| [Bruno](agents/bruno.md) | Back end: schema, access rules, APIs, performance | Builds | Every prompt sent, anything that loosens access or drops data |
| [Quinn](agents/quinn.md) | QA: test plans, exploratory tests, bug log | Reviews what Maggie and Bruno build | Anything that spends money or touches real accounts |
| [Security auditor](agents/security-auditor.md) | Independent security review before launch | Reviews what Bruno builds | Nothing to send. Reports only |
| [Researcher](agents/researcher.md) | Competitor and market research from public sources | Neither | Nothing to send. Public sources only |
| [Legal advisor](agents/legal-advisor.md) | Drafts terms and disclaimers, flags legal risk. Not a lawyer | Neither | Everything needs a lawyer's review before use |
| [Marketing writer](agents/marketing-writer.md) | Landing page, content, and SEO copy in my voice | Neither | Drafts only. I publish |

## Skills
- [product-designer](skills/product-designer/SKILL.md) and [product-manager](skills/product-manager/SKILL.md): advice and documents only. Design reviews, A/B plans, briefs, PRDs, and prioritization. They never change the build.
- [session-handoff](skills/session-handoff/SKILL.md): a fixed end-of-session summary so a fresh session can pick up where the last one stopped.
- [agent-operator](skills/agent-operator/SKILL.md): a decision guide for when to use subagents, teams, worktrees, or workflows.
- [case-study-steps](skills/case-study-steps/SKILL.md): turns a messy account of my work into at most three steps for a website.
- [writing-check](skills/writing-check/SKILL.md): audits a draft against my voice rules before it goes out.
- [roast](skills/roast/SKILL.md): five opposing personas attack an idea, then a judge gives one verdict and the cheapest test.
- [grill-me](skills/grill-me/SKILL.md): interviews me one question at a time and saves each answer to a file as it goes.

## Decisions
- [decisions/](decisions/) holds short records of why the setup is the way it is. Start with the approval gate for build prompts.

## How to read it
- Start with [Quinn](agents/quinn.md) for how review stays independent.
- Then [Maggie](agents/maggie.md) for the approval gate.
- Tool names such as `mcp__lovable__send_message` are generic placeholders for real connectors.

## Credits
- Full notice in [NOTICE.md](NOTICE.md). License: MIT, see [LICENSE](LICENSE).
- The grill-me and session-handoff skills are adapted from Nate Herk's public repositories, used under the MIT license (see [NOTICE.md](NOTICE.md)).
- The roast skill is adapted from Naim Katiman's public repository, used under the MIT license (see [NOTICE.md](NOTICE.md)).
- The agent-operator skill summarizes the official Claude Code docs (https://code.claude.com/docs).

## About Aisle
- Aisle is a working name for an unpublished prototype that estimates bouquet prices from public wholesale data.
- Estimates are illustrative and not quotes. Nothing here has been validated with florists yet.
