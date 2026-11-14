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
- `context/docs/research/`: raw research (company, customers, competitors, market, signals, voice) with URLs. Read for a fact and its citation. `context/docs/case-studies.md`: customer stories (none found yet).
- `knowledge-base/playbooks/`: step-by-step plays for repeatable motions. Read before running a motion.
- `knowledge-base/learnings/`: what worked, what failed, and why. Read before repeating or redesigning a motion.
- `meetings/`: meeting notes and transcripts. Read for decisions, objections and customer language.
- `output/campaigns/`: finished campaign assets and drafts. Read to reuse or check past work.
- `output/outbound/`: outbound sequences, emails and call scripts. Read to reuse or check past outbound work.
- `output/social/`: social posts and content drafts. Read to reuse or check past social work.
- `output/data/`: exported lists, matrices and analysis outputs. Read when you need generated data.
- `inspiration/`: ads and examples to learn from. Read before writing copy or designing a campaign, for patterns to borrow from.
- `tools/`: scripts, integrations and tool configs. Read before building or running automations.
- `weekly-priorities/`: one file per week (YYYY-Www.md) listing priorities. Read at the start of every session.
- `work-log/`: one file per week with timestamped entries of every change. Read to see what changed and when.

## Rules

- Cite a source (URL or file path) for every company fact.
- Never invent numbers. If a figure is unknown, say so.
- No em dashes in any copy.
- Ask before sending or publishing anything.
- Log every change in this week's work log.

## Tools

- treg (CLI): paid data lookups. Check the price with `treg catalog get <id>` before every call, and report the cost after.
- Miro (MCP): diagrams and GTM flowcharts.
- Notion (MCP): where finished docs are published. GitHub stays the source of truth.
