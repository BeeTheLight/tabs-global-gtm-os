# Tabs Global: outbound GTM system

End-to-end outbound design, rebuilt 2026-11-13 from `context/icp/` (icp.md, personas.md, signal-matrix.md v3) and the files they cite. Educational design from public sources, not affiliated with Tabs Global. Tags: [icp], [personas], [matrix], [facts], [messaging], [market], [competitors] = the file in context/. INFERRED = design choice or reading not supported by the research. "tune" = a starting value to adjust after real data, not a fact. PROXY = evidence from Verto or WeWire, the incumbents used as stand-ins because Tabs has no customers or case studies on record.

**Decided 2026-11-13 by the owner:** segment A (CBN-registered operators and Nigerian cross-border fintechs) runs first; D (African-HQ platforms, marketplaces, brokers, exchanges) is the second, smaller test. [matrix]

**Miro board:** [Tabs global GTM System](https://miro.com/app/board/uXjVEOZgdq0=/) (new board, created 2026-11-13). Spec `diagrams/tabs-global-gtm-system.json`, built to `diagrams/tabs-global-gtm-system.svg`: 45 boxes, 50 links, no overlaps, 157 board items, none failed. It shows 13 decisions in five rows, including the two that the earlier chart left out (domain found, inbox health) and the CRM and weekly-loop decisions. Layout has not been checked by eye yet. An earlier board "Tabs global GTM System" (https://miro.com/app/board/uXjVEOaZi_w=/) still exists with the previous v2 chart (spec `diagrams/tabs-global-gtm-system-v2.json`); it is superseded by the board above and has not been deleted.

## Tools and what is connected today
| Tool | Job in this system | Connected today |
|---|---|---|
| Claude Code | Runs skills, writes and QA-checks copy, classifies replies, reviews results, updates the Context OS | Yes |
| GitHub | Source of truth for the Context OS; versioned, reviewed changes | Yes (repo BeeTheLight/tabs-global-gtm-os) |
| Clay | Tables for signals, enrichment, people and email waterfalls | Not confirmed; skills are installed |
| HubSpot | CRM, suppression, pipeline | Not connected (its MCP server failed to connect) |
| n8n | Weekly schedules, webhooks, weekly export | Not confirmed |
| PlusVibe | Email sending and reply capture | Not confirmed |
| treg (inside Claude Code or Clay) | Paid lookups: LinkedIn jobs ($0.00045 per search), LinkedIn company profile (about $0.001), Apollo free people search | Yes, tested on 2026-11-13 |
Where this doc says Clay, HubSpot, n8n or PlusVibe, the step is designed but not yet runnable.

## The system at a glance
Context OS, then buying signals, then finding companies, enrichment, the ICP fit check and routing by segment; then finding people, finding and verifying emails, the sequence; then reply handling, the CRM and the weekly feedback loop back into the Context OS. Five workflows are planned (W1 to W5, see the end). Each step below lists what happens, the tool, and every decision with where each answer leads.

## The system in order

### 1. Context OS
- **What:** The single source for who we target and what we may say: icp.md (five segments, hard exclusions), personas.md, signal-matrix.md v3, positioning, messaging.md, and facts.md as the only allowed source of claims. Everything downstream reads it first.
- **Tool:** Claude Code reads and edits; GitHub stores and versions.
- **Decisions:**
  - Is the claim we want in facts.md and approved? **Yes:** copy may use it. **No:** it becomes a placeholder and the copy waits. On 2026-11-13 the owner approved claims F1 to F13 and the value-prop line; the numbers, logos, sender identity and CTA are still unapproved, and P3 is proposed only.
  - Is the segment priority current? **Yes:** run it (today: A first, D second test). **No:** refresh the matrix first.
  - Is the evidence for a segment Tabs' own or proxy? **Tabs' own:** treat as validated. **Proxy:** label it and test it before scaling (D and E are proxy only).

### 2. Buying signals
- **What:** Scheduled runs of the verified signals in [matrix]:
  - **U2** hiring cross-border payments, payouts or FX roles at Nigerian operators (feeds W1).
  - **U1** "Payment Partnerships Manager (Africa)" roles at platforms and brokers (W3); seen 2026-11-13 at FxPro, Luno, Nilos.
  - **U3** Africa roles at non-African companies (W4).
  - **N2** CBN payments circular of 2026-06-15: market-structure compliance by 2026-12-31 and data localisation by 2027-01-01 (W2); **N3** IMTO naira settlement directive, effective 2026-05-01 (W5).
  - **N1** the CBN registers are the account list, not a trigger.
  - Held back: U4 new leaders, U5 funding, U6 headcount growth, L1 lookalike; A7 competitor launches and X1 incumbent complaints are message research, not list sources.
- **Tool:** n8n triggers weekly; Clay or treg `crawl4ai.linkedin.search.jobs` pulls the results ($0.00045 per search).
- **Decisions:**
  - Is the signal VERIFIED in the matrix? **Yes:** switch it on. **No:** it stays in the backlog.
  - Is the hit fresh (posted within 30 days, tune)? **Yes:** go to step 3. **No:** wait for the next run.

### 3. Finding companies
- **What:** Turn hits into accounts. Match hirers to the CBN PSP register (279) and IMTO register (108), 387 names in all, for segment A; keep unmatched hirers as D or C candidates until the HQ check in step 6. A first sample matched one name: Belyfted Limited (IMTO entry 7) hiring a developer in Lagos on 2026-10-27. [matrix]
- **Tool:** Clay (with treg lookups).
- **Decisions:**
  - Does the name match a register entry? **Yes:** tag as an A candidate. **No:** hold as a D or C candidate.
  - Is the company already in HubSpot (customer, open deal, or contacted in the last 90 days, tune)? **Yes:** skip, or hand to the account owner. **No:** continue.

### 4. Enrichment
- **What:** Add domain, headcount, HQ country, register category, a competitor flag, and persona counts from Apollo free search. Size is Not found for the ICP, so collect it now and set bands after the first 50 accounts. [icp]
- **Tool:** Clay with treg `linkedin.company.profile` (about $0.001 per call) or `crawl4ai.companies.enrich` ($0.00115 per call).
- **Decisions:**
  - Domain found? **Yes:** continue. **No:** one retry by name, then drop and log.
  - Competitor flag set (Verto, WeWire, Nomba, Kora, Fincra, Flutterwave, Yellow Card, Thunes, Raenest, Grey, Afriex, Cleva, WorldFirst, plus PingPong Payments, XTransfer, Duplo, Airwallex, Wise, Payoneer)? **Yes:** goes to the fit check as a drop. **No:** continue. [competitors]

### 5. ICP fit check
- **What:** Apply the hard exclusions and fit rules from [icp]: businesses only; not an individual, freelancer or consumer product; not a provider selling the same B2B product; passes KYB-type checks (no shell companies, sanctioned persons); country Tabs can serve (Nigeria first; the other five named markets are unconfirmed live). Consumer remittance apps are not excluded: Lemfi, Taptap Send and Chipper Cash are Verto customers, so they are PROXY buyers of payout rails. [matrix]
- **Tool:** Clay formula column, reviewed in Claude Code.
- **Decision: ICP fit?**
  - **Yes:** go to routing (step 6).
  - **No:** drop and write the reason to the table; the weekly review reads these.
  - **Unsure (missing data):** park for manual review, capped (tune); do not send.

### 6. Routing by segment
- **What:** One workflow family, five segments, because the build is shared and only keywords and angle change. The exclusivity rule from [matrix]: on a CBN register means A; otherwise a non-African HQ means C; otherwise an African-HQ platform, marketplace, broker or exchange means D; otherwise trade businesses (B) and foreign-currency-account seekers (E) are parked.
- **Tool:** Clay routing column (HQ lookup from enrichment).
- **Decision: Segment?**
  - **A, on a CBN register:** high priority, runs first (decided). Angles: one endpoint per market; collect naira and lock a quote for 60 seconds; screening and name checks before money moves, ahead of the end-2026 CBN dates. [matrix]
  - **D, African-HQ platform (PROXY evidence):** medium, runs as a small second test alongside A. Angle: one integration for virtual accounts, conversion and payouts.
  - **C, non-African payer:** medium, low confidence; heavy exclusion needed because most hits are providers.
  - **B and E, parked:** no observable data source; hold until one exists.

### 7. Finding people
- **What:** For each account find the three personas from [personas]: champion (engineering or product), economic buyer (finance, operations or commercial), influencer (compliance or treasury). Titles are INFERRED for Tabs; PROXY titles at Verto's customers are CTO (Cowrywise), CEO (Triply) and Commercial Director (Target Mart), so in small firms the economic buyer may be a founder. Segment B has no engineer persona.
- **Tool:** Clay with Apollo free people search through treg (returns no emails or tenure).
- **Decision: Persona found?**
  - **Champion or economic buyer found:** continue.
  - **Only the influencer found:** continue with the compliance angle, flagged.
  - **None found:** keep the account only; retry on the next run; do not send.

### 8. Finding and verifying emails
- **What:** Look up work emails, then verify. A found email is the provider's best match, not confirmed. Check the domain matches the company. The email provider and verifier are not chosen yet.
- **Tool:** Clay waterfall with a verifier.
- **Decision: Email valid?**
  - **Valid, domain matches:** go to step 9.
  - **Risky or catch-all:** LinkedIn only for that person.
  - **Invalid or none:** LinkedIn only; drop if there is no profile.

### 9. The sequence (email and LinkedIn)
- **What (write):** Claude Code drafts one email sequence and LinkedIn touches per persona, only from an approved structure (`/build-workflow-spec`, then `/campaign-copy`) and only with wording from [facts]. No competitor names, no price, no volume figure, no "bank" language, no proxy facts, no em dashes. `/campaign-qa` checks the result.
- **What (send):** PlusVibe sends a 3-email sequence (tune); LinkedIn touches go manually from the sender profile because no LinkedIn tool is chosen. First batch is small (tune).
- **Tool:** Claude Code (write, QA); PlusVibe (email); sender profile (LinkedIn).
- **Decisions:**
  - Is every claim in facts.md? **Yes:** continue. **No:** replace with a placeholder or cut.
  - Is the copy approved by a human? **Yes:** go on to sending. **No:** fix and re-check. Rule from CLAUDE.md: ask before sending anything.
  - Is inbox health OK and sender identity set? **Yes:** launch the small batch. **No:** pause; the sender fields in [facts] are still placeholders.
  - CTA: not decided; pick one before launch (Tabs' own: "Get a demo", "Read the docs", "Talk to us").

### 10. Reply handling
- **What:** Replies flow from PlusVibe through an n8n webhook to a classifier in Claude Code (not built yet), then to a human for anything that needs an answer.
- **Tool:** n8n, Claude Code, HubSpot update.
- **Decision: Reply?**
  - **No reply by the end of the sequence:** end; re-enter only on a new signal.
  - **Positive:** a human replies the same day (tune) and offers the demo link; open a HubSpot deal.
  - **Not now:** snooze 90 days (tune); re-enter on a new signal.
  - **Wrong person:** ask for the right contact; re-route to the correct persona.
  - **Objection:** match to [personas] objections (new company, no named customers, no public pricing, unnamed partner banks, and INFERRED comparisons with Verto's and WeWire's published fees, licences and ISO 27001); a human answers; log the objection. Never name a competitor unless a human decides to.
  - **Stop or bounce:** suppress in PlusVibe and HubSpot; never contact again.

### 11. CRM
- **What:** HubSpot holds every account, person and deal, plus the fields the loop needs: workflow W#, signal ID, segment, persona, angle, sequence version, reply class. Stages are INFERRED: Lead, Contacted, Replied, Meeting booked, Qualified, Won, Lost.
- **Tool:** HubSpot (not connected; its MCP server failed to connect).
- **Decisions:**
  - Meeting held? **Yes:** qualify. **No:** one reschedule, then back to Contacted.
  - Qualified (matches the ICP)? **Yes:** open an opportunity. **No:** Lost with a reason.
  - Closed? **Won or Lost:** record the reason; it feeds step 12.

### 12. Weekly feedback loop into the Context OS
- **What:** Every week n8n exports results from PlusVibe and HubSpot; Claude Code reviews them by workflow, signal, segment, persona and angle, updates the files that drove the result, commits to GitHub and logs the change in the work log.
- **Tool:** n8n (export), Claude Code (review and edits), GitHub (commit).
- **Decisions:**
  - Did a signal produce replies? **Yes:** keep and scale. **No after enough sends (tune):** pause or kill, and record why in signal-matrix.md.
  - Does D come within reach of A's reply rate (threshold tune)? **Yes:** promote D. **No:** keep A first and D small.
  - Did replies confirm or contradict the proxy hypotheses (segments D and E, persona titles)? **Confirm:** raise the evidence rating. **Contradict:** lower it and revise icp.md.
  - New objection or wording that worked? **Yes:** update personas.md, messaging.md and, after approval, facts.md. **No:** leave.
  - Does a closed-lost reason show a bad-fit pattern? **Yes:** add it to icp.md "Not a fit". **No:** leave.
  - Data problems (bounces, wrong titles, missing sizes)? **Yes:** fix the source table before the next run.

## Check against the four pillars
| Pillar | How the design meets it | Gap today | Fix |
|---|---|---|---|
| Clean data | Facts gate for every claim; proxy facts barred from copy; dedupe against HubSpot; competitor exclusion list; email verification; suppression list; Context OS versioned in GitHub | No Tabs customer data, no company size, persona titles INFERRED (proxy titles only); CRM not connected; several earlier quotes could not be re-confirmed (see facts.md) | Interview or find buyers; set size bands after 50 accounts; connect HubSpot; approve or drop each unverified quote |
| Always-on signals | n8n weekly runs of U1, U2, U3; register list N1 plus circular deadlines N2 and N3 | U1 to U3 are VERIFIED (PARTIAL) with noisy jobs data; N1 to N3 are VERIFIED (COMPOUND); Clay and n8n not confirmed; N2 rests on news summaries of the circular; U4 and U5 untested | Connect Clay and n8n; read the CBN circular text; tighten U2 keywords |
| Composable workflows | One jobs-search build serves U1, U2 and U3 with keyword and location swaps; one register scrape serves N1 to N3; each step is its own module; routing branches by segment | No workflow spec saved yet; LinkedIn tool undecided; email provider undecided | Run `/build-workflow-spec` for W1; choose a LinkedIn tool and an email waterfall |
| Tight feedback loops | Weekly review writes back to icp, personas, messaging, matrix and facts, then commits; A versus D comparison and proxy-hypothesis checks are explicit decisions | No baseline reply rate; thresholds are "tune"; reply classifier not built | Set baselines after roughly the first 200 sends (tune); build the classifier in n8n |

## Planned workflows (from the matrix)
| W # | Workflow | Segment | Steps it uses |
|---|---|---|---|
| 1 | Cross-border payments hiring at CBN-registered operators (N1 + U2) | A | 2 to 12 |
| 2 | CBN circular deadline exposure by register category (N1 + N2) | A | 2 to 12 |
| 3 | Payment Partnerships (Africa) roles at platforms and brokers (U1) | D | 2 to 12 |
| 4 | Africa roles outside Africa (U3) | C | 2 to 12 |
| 5 | IMTO naira settlement exposure (N1 + N3) | A | 2 to 12 |
W1 is the first to build.

## Open questions
- Which tools will actually be connected, and who owns each?
- LinkedIn sending: which tool, or manual?
- Email provider and verifier for the waterfall.
- Who signs off copy before launch? (The owner approved facts.md claims F1 to F13 on 2026-11-13; Tabs Global itself has not reviewed anything.)
- CTA for email 1, and who answers a prospect who asks for pricing on the first reply (both incumbents publish prices or plans).
- Thresholds for signal kill, snooze length, sample size and the A versus D promotion test.
