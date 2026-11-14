# Tabs Global GTM Context OS

## Company

Tabs Global is a cross-border payments platform for businesses moving money into and out of Africa, with an API product called Tabs Connect (source: https://tabsglobal.co/, research in `context/docs/research/company.md`).

## How this folder works

- `.claude/skills/`: reusable skills for repeatable GTM tasks. Read when running a known workflow.
  - `/signal-matrix`: build ICP and signal matrices.
  - `/campaign-strategy`: generate outbound campaign ideas with priorities.
  - `/build-workflow-spec`: turn one play into a full workflow spec.
  - `/campaign-copy`: write cold email and LinkedIn copy from an approved spec.
  - `/campaign-qa`: QA a Clay table or email campaign against its spec.
  - `/campaign-contract`: write the Clay build sheet for one campaign.
  - `/prompt-builder`: build per-row prompts for Clay AI columns.
  - `/clay-build-plan`: step-by-step Clay build guide plus flow diagram.
  - `/design-clay-table-json`: write Clay table JSON from a contract.
  - `/import-clay-table`: import a table JSON into Clay and test it.
  - `/save-clay-schema`: save an approved Clay table to the local registry.
  - `/build-clay`: build or repair a production Clay outbound workbook.
  - `/export-tables`: export Clay tables to local CSV.
  - `/calculate-costs`: report one Clay table's spend and credits.
  - `/workspace-cost-audit`: report a Clay workspace's monthly spend.
  - `/inbox-placement-test`: test cold email inbox placement per sender pool.
  - `/miro-gtm-flowchart`: draw a GTM system as a Miro flowchart.
  - `/agent-browser`: drive a browser to fill forms and pull data.
  - `/crawl4ai`: crawl sites into Markdown or JSON, free and local.
- `context/icp/`: `icp.md`, `personas.md`, `signal-matrix.md`. Read before targeting, list building or scoring.
- `context/positioning/`: `positioning.md`, `value-proposition.md`, `competitors.md`. Read before writing any pitch or copy.
- `context/messaging/`: `messaging.md`, `facts.md` (approved claims, the copy gate). Read before drafting any outbound or content.
- `context/brand-kit/`: `brand.md` (voice, key phrases). Read before producing any copy or design.
- `context/docs/research/`: raw research (`company.md`, `customers.md`, `competitors.md`, `market.md`, `signals.md`, `voice.md`) with URLs. Read for a fact and its citation. `context/docs/`: `case-studies.md` (none found yet), `gtm-system.md` (outbound system design, Miro link inside).
- `knowledge-base/playbooks/`: step-by-step plays for repeatable motions. Read before running a motion. Files: `workflow-anatomy.md` (4-layer anatomy, Mother Intent Catalog), `signal-matrix-framework.md`, `copy-iron-laws.md`, `copy-frameworks.md`, `linkedin-dm-frameworks.md`, `copy-bans.yaml` (banned characters, words, phrases), `templates/facts-template.md`, and `clay/` (`actions-data-credits.md`, `expert.md`, `formulas.md`, `iron-laws.md`, `prompts.md`).
- `knowledge-base/learnings/`: what worked, what failed, and why. Read before repeating or redesigning a motion.
- `meetings/`: meeting notes and transcripts. Read for decisions, objections and customer language.
- `output/campaigns/`: finished campaign assets and drafts. Read to reuse or check past work. Files: `campaign-strategy.md` (19 ideas, claim map), `cross-border-payments-hiring-registered-operators/workflow-spec.md` (W1 spec plus approved copy, status COPY-APPROVED).
- `output/outbound/`: outbound sequences, emails and call scripts. Read to reuse or check past outbound work.
- `output/social/`: social posts and content drafts. Read to reuse or check past social work.
- `output/data/`: exported lists, matrices and analysis outputs. Read when you need generated data.
- `inspiration/`: ads and examples to learn from. Read before writing copy or designing a campaign, for patterns to borrow from.
- `diagrams/`: flowchart specs and SVGs (Miro). Read before redrawing the GTM system. Files: `tabs-global-gtm-system.json` and `.svg` (current), `tabs-global-gtm-system-v2.json` and `.svg` (older version). Miro board: https://miro.com/app/board/uXjVEOZgdq0=/ (current; an older board, https://miro.com/app/board/uXjVEOaZi_w=/, still exists).
- `tools/`: scripts, integrations and tool configs. Read before building or running automations. Folders: `agent-browser/`, `crawl4ai/`, `rex/` (Clay client, cost scripts, ClayLens extension, table registry).
- `weekly-priorities/`: one file per week (YYYY-Www.md) listing priorities. Read at the start of every session.
- `work-log/`: one file per week with timestamped entries of every change. Read to see what changed and when.
- Root files: `README.md`, `.gitignore` (ignores `.env`, `.treg/`, CSVs, `.claude/settings.local.json`), `.env` (empty, gitignored), `.mcp.json` (project MCP config, not committed), `.claude/settings.json` (Miro plugin), `.claude/settings.local.json` (treg config path, gitignored).

## Rules

- Cite a source (URL or file path) for every company fact.
- Never invent numbers. If a figure is unknown, say so.
- No em dashes in any copy.
- Ask before sending or publishing anything.
- Log every change in this week's work log.

## Tools

- treg (CLI): paid data lookups. Check the price with `treg catalog get <id>` before every call, and report the cost after.
- Miro (MCP): diagrams and GTM flowcharts.
- Notion (MCP): where finished docs are published. GitHub stays the source of truth. Published tree, "TABS  GTM OS" (under GTM Learnings): https://app.notion.com/p/4186336cbd0181478f6dc19fd36004b2?pvs=204
- Miro (MCP, claude.ai connector and miro@miro-ai plugin): current board https://miro.com/app/board/uXjVEOZgdq0=/.
- treg (MCP): same lookups as the CLI; config in `.treg/` (gitignored).
- Claude Code and GitHub (https://github.com/BeeTheLight/tabs-global-gtm-os): the Context OS and its source of truth.
- Local tools in `tools/`: `crawl4ai` (free local crawling), `agent-browser` (browser automation), `rex` (Clay scripts and ClayLens).
- Planned in the system design, not connected yet: Clay, HubSpot, n8n, PlusVibe (see `context/docs/gtm-system.md`).
