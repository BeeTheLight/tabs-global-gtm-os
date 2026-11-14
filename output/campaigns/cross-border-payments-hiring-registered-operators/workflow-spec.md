# Workflow spec W1: Cross-border payments hiring at CBN-registered operators

**Status:** COPY-APPROVED 2026-11-13 · open items: F12 and F13 wording, C5 and C6 claim choice, sender identity

Built with `/build-workflow-spec` from campaign-strategy idea #4 (`output/campaigns/campaign-strategy.md`), `context/icp/icp.md`, `personas.md`, `signal-matrix.md` v3, `context/messaging/facts.md` (claims F1 to F13 approved by the owner on 2026-11-13) and the measured data below. This file contains structure only. It has no copy: `/campaign-copy` writes narrative from the approved angles. Sections are tagged [ENGINE] (reusable) or [ICP] (the part that changes for another segment).

---

## 1. Mother Intent (Trigger) [ENGINE]
A CBN-registered payment operator has posted a role in the last 30 days for a function that touches payments (engineering or product, finance or operations, compliance, or partnerships and business development). Catalog intent: **Hiring specific roles** (`knowledge-base/playbooks/workflow-anatomy.md`).

## 2. Inclusion / Exclusion [ICP]

**Include**
- **ICP box (segment A, from icp.md and signal-matrix v3):** the company's normalized name matches an entry on the CBN PSP register (parsed on 2026-11-13: 246 entries) or the CBN IMTO register (108 entries). The register is the filter. Businesses only.
- **Deviation from the matrix (approved by the owner 2026-11-13):** the matrix defines A as "Nigeria-based". The IMTO register also lists foreign companies that hold a CBN licence (for example Taptap Send UK Limited and Remitly Inc.). This spec includes any register match, whatever its HQ, because the licence is the observable fact and the exclusivity rule in the matrix already says "on a register means A".
- **Trigger definition:** a LinkedIn public job posting at that company, posted within 30 days (tune), in any location, whose title falls in one of the four role families in section 4.
- **Recipient (from personas.md, chosen by the role family of the posting):**
| Role family of the posting | Recipient persona | Why |
|---|---|---|
| ENG_PRODUCT | Champion (head of product or payments engineering) | The hire is the champion's team |
| FIN_OPS | Economic buyer (finance or operations lead) | The hire is in their function |
| COMPLIANCE | Influencer (compliance, risk or treasury lead) | The hire is in their function |
| PARTNERSHIPS_BD | Economic buyer (commercial lead or founder) | Proxy titles at comparable companies: CEO, Commercial Director |
One recipient per account per send. If that persona is not found, fall back to the other persona with the nearest function, in this order: economic buyer, then champion, then influencer; if none is found, do not send (the account is kept and retried next run).

**Exclude**
- **Providers selling the same B2B product, and adjacent providers:** Verto, WeWire, Nomba, Kora, Fincra, Flutterwave, Yellow Card, Thunes, Raenest, Grey, Afriex, Cleva, WorldFirst, PingPong Payments, XTransfer, Duplo, Airwallex, Wise, Payoneer. (icp.md, competitors research.)
- **Card networks:** register category "Card/Payment Schemes", and the names Visa and Mastercard (including Mastercard Transaction Services). They are on the register but are not buyers.
- **Companies shown in the "Trusted by" row on Tabs' homepage** (Hercle, Nomba, Currency Solutions, Paystack, Grey, Sterling) until each is confirmed or cleared, so we never cold-email a possible existing relationship.
- **Active pipeline:** any company in HubSpot as a customer, in an open deal, or contacted in the last 90 days (tune). HubSpot is not connected, so until it is, this is a manual suppression file.
- **Recruitment agencies and staffing firms:** removed automatically, because they do not match the registers.
- **Consumer remittance apps are NOT excluded.** Taptap Send and Remitly are on the IMTO register; comparable apps are customers of the incumbents (proxy evidence), so they buy payout rails.

## 3. Sources [ENGINE]

**Trigger source**
- LinkedIn public job search through treg `crawl4ai.linkedin.search.jobs` ($0.00045 per call, price checked 2026-11-13). Fields returned: company, job title, location, posted date, link. No company domain, no description text.
- Queries (run weekly, each with posted-within-a-month): `cross-border payments`, `payouts`, `settlement`, `remittance`, `foreign exchange`, `partnerships Africa`, `compliance MLRO`, `payments product`, `payments engineer`; locations Nigeria, United Kingdom, United States. The start offset is ignored by the tool, so coverage comes from varying queries, not paging.

**Account list (ICP filter)**
- CBN PSP register: https://www.cbn.gov.ng/PaymentsSystem/PSPs.html and IMTO register: https://www.cbn.gov.ng/PaymentsSystem/InternationalMoneyTransferOperators.html. HTML tables, names (and for IMTOs addresses) only, no dates. Re-pulled by script on 2026-11-13: 354 names parsed (246 PSP, 108 IMTO). Free.

**Name join (deterministic)**
- Normalize both sides: lowercase, remove text in brackets, remove punctuation, remove the words limited, ltd, inc, plc, group, technologies, technology, solutions, services, financial, payment, payments, holdings, global, international, systems, company, nigeria, uk. A job employer matches a register entry when the normalized strings are equal, or when an entry in the alias table (below) maps them. No fuzzy matching.
- **Alias table, seeded from measured matches (register spelling in capitals as listed):** Paystack to "Paystack Payment Limited"; Kredete to "KREDETE TECHNOLOGY LIMITED"; Belyfted to "BELYFTED LIMITED"; PalmPay to "PalmPay Limited"; Taptap Send to "TAPTAP SEND UK LIMITED"; Remitly to "REMITLY INC."; Nomba to "Nomba Financial Services Limited". Unmatched employers (for example Moniepoint Group, PayZeep, Cardtonic in today's pulls) are not on the parsed registers under those names and do not enter the workflow; check an alias before concluding they are absent.

**Enrichment sources**
- Company domain and headcount: treg `linkedin.company.profile` (about $0.001 per call) or `crawl4ai.linkedin.company.profile` ($0.0009). The job card carries no company URL, so the domain lookup by company name is untested.
- People: Apollo free people search through treg (no emails, no tenure); per-company lookup by organisation name is untested.
- Emails: Clay waterfall with a verifier; provider not chosen.

**Measured on 2026-11-13 (7 jobs searches, 66 distinct employers, joined to the 354 register names with a crude first-word match):** 10 employers matched a register name: Paystack, Visa, Kredete, Belyfted, Nomba, PalmPay, Taptap Send, Duplo, Remitly, Mastercard. After the exclusions above (Visa and Mastercard as networks, Nomba as a competitor and logo, Duplo as an adjacent provider, Paystack as a logo until cleared), 5 remain: Kredete, Belyfted, PalmPay, Taptap Send, Remitly. Under the trigger and role-family rules in sections 4 and 5, 4 would have triggered: Kredete (Banking Partnerships Manager, UK listing), PalmPay (Anti-Fraud Manager), Taptap Send (Head of Partnerships (Africa)), Remitly (Head of Global Expansion). A payment keyword in the job title matched **none** of the register-matched companies. Belyfted (Full Stack Developer) and Paystack (QA Lead, Head of Finance and others) matched a register entry but posted only generic engineering or finance titles, so they do not trigger. The first-word match also produced false matches (Visa, Mastercard), which is why the spec requires an exact normalized match plus the alias table. The searches were not designed for this workflow, so treat 4 triggered accounts per month as a floor, not a forecast.

## 4. Signals table [ENGINE]

Every read is a boolean or a regex on a field that the sources return. Regexes are case-insensitive and applied to the job title.

| # | Signal | Role | How it's read | Output |
|---|---|---|---|---|
| S1 | Employer is on a register | trigger (gate) | Normalized name equals a normalized register entry, or alias table hit, and the company is not excluded | boolean; plus `register_category` (PSP category name, or "IMTO") |
| S2 | Posting is fresh | trigger | `posted_on` within the last 30 days (tune) | boolean |
| S3 | Role family | router | First match, in this order, on the title: **COMPLIANCE** `compliance\|MLRO\|AML\|risk\|regulatory\|fraud`; then **PARTNERSHIPS_BD** `partnership\|partner manager\|business development\|\bBD\b\|country manager\|expansion`; then **FIN_OPS** `finance\|financial\|treasury\|accountant\|accounting\|reconciliation\|settlement\|operations\|controller\|CFO`; then **ENG_PRODUCT** `engineer\|developer\|architect\|devops\|\bSRE\b\|product manager\|product owner\|head of product\|head of engineering\|CTO`; otherwise NONE | enum: COMPLIANCE, PARTNERSHIPS_BD, FIN_OPS, ENG_PRODUCT, NONE |
| S4 | Payment term in the title | router | Title matches `payment\|payments\|payout\|payouts\|cross-border\|remittance\|foreign exchange\|\bFX\b\|forex\|settlement\|corridor` | boolean (precise = true) |
| S5 | Register category | context-clause | Copied from S1; never routes | text |
| S6 | Role title and location | context-clause | Copied from the job card; never routes | text |

**Trigger rule:** the workflow fires for an account when S1 and S2 are true and S3 is not NONE and (S4 is true or S3 is COMPLIANCE or PARTNERSHIPS_BD). Generic engineering and generic finance titles (S4 false, S3 ENG_PRODUCT or FIN_OPS) do not fire: they are the hiring-velocity idea (Tier 3), which is too weak to send on.

**Count clusters:** none. No count routes in this workflow, so no raw count reaches copy.

## 5. Routing matrix with angles [ENGINE]

Two axes, named by the structure itself: role family (4) times payment term in the title (2) = **8 cells**. Six fire, two do not. "Angle" is meaning, not copy. Claim IDs refer to `context/messaging/facts.md`; copy may use only those.

| Cell | Deterministic read | What it tells us (inferred situation) | The angle it earns |
|---|---|---|---|
| C1 | S3 = ENG_PRODUCT and S4 = true | The company is building or extending payments functionality now: an engineering or product role with a payment term in its title. We infer what they are doing, not how it feels. Recipient: champion | A way to add corridors without a new build per market: one endpoint per market, start with one market and keep the same integration. Claims F1, F2; F6 for a developer recipient. Uses `{{role_title}}` |
| C2 | S3 = FIN_OPS and S4 = true | The company is adding operations or finance capacity for payment flows (settlement, reconciliation, payments operations). Recipient: economic buyer | Money that settles into one ledger in the preferred currency, with naira collected locally and a locked quote before committing. Claims F8, F12, F13. Uses `{{role_title}}` |
| C3 | S3 = COMPLIANCE and S4 = true | The company is adding compliance capacity specifically for payments. Recipient: influencer | Screening and monitoring inside the payment flow with audit trails, and recipient names verified before money moves. Claims F9, F4. Uses `{{role_title}}`. No claim about any CBN rule |
| C4 | S3 = COMPLIANCE and S4 = false | The company is adding compliance, risk or fraud capacity; the title does not say payments. The role is the only evidence, so the angle cannot assume a payments focus. Recipient: influencer | Same meaning as C3 but anchored only on the role: checks run inside the payment flow (F9) and names are verified before money moves (F4). Must not say "your payments compliance". Uses `{{role_title}}` |
| C5 | S3 = PARTNERSHIPS_BD and S4 = true | The company is adding a payments partner or rail for new markets, for example a payment partnerships role for Africa. Recipient: economic buyer | One integration for the markets they are adding: one endpoint per market, start with one market. Claims F1, F2. Uses `{{role_title}}` |
| C6 | S3 = PARTNERSHIPS_BD and S4 = false | The company is expanding commercially (partnerships, expansion, country management); no evidence about payment rails. Recipient: economic buyer | Start with one market and keep the same integration, one endpoint per market. Claims F1, F2. Must not assume a payments gap. Uses `{{role_title}}`, `{{role_location}}` |
| C7 | S3 = ENG_PRODUCT and S4 = false | A generic engineering hire at a register operator; the posting says nothing about payments | **No send.** Logged for the weekly review only, so we can test later whether it deserves a route |
| C8 | S3 = FIN_OPS and S4 = false | A generic finance or operations hire | **No send.** Logged for the weekly review only |

**Branch coverage.** Every firing cell has a job posting, so `{{role_title}}` and `{{role_location}}` exist in C1 to C6. C4 and C6 have no payment term in the title, so their angles do not mention payments in the role. Naira collections (F13) appear only in C2, where the recipient runs finance or operations. No cell uses headcount, funding, corridors, volumes or the job description, because none is delivered.

**Niche-native test.** Every firing angle is anchored on a specific role posted by a CBN-registered operator in the last 30 days; no other company category could send it unchanged.

## 6. Variables contract [ENGINE]

| Variable | Source field | Exists in branches |
|---|---|---|
| `{{first_name}}` | Apollo people search, recipient first name | C1 to C6 (no send if the recipient is not found) |
| `{{company_name}}` | Register entry, display form with legal suffix removed | C1 to C6 |
| `{{role_title}}` | Job card title | C1 to C6 |
| `{{role_location}}` | Job card location, city only: the text before the first comma (for example "Lagos" from "Lagos, Lagos State, Nigeria") | C1 to C6 |
| `{{role_posted_date}}` | Job card `posted_on` (copy may say "recently", not an exact day count) | C1 to C6 |
| `{{register_category}}` | Register page: PSP licence category or "IMTO" | C1 to C6 (context-clause only) |
| `{{sender_name}}`, `{{sender_title}}`, `{{signature}}`, `{{cta}}` | `context/messaging/facts.md` placeholders, not yet filled | All |

**Not delivered, so copy may never use:** revenue, headcount, funding, technology stack, corridors, volumes, the text of the job description, or any CBN rule detail (market dates are in the research, not in facts.md, so they are not authorised copy facts).

## 7. Cadence and channel [ENGINE]

- **Periodicity:** always-on. n8n runs the searches weekly (not confirmed connected); the register list is re-pulled monthly.
- **De-duplication:** one send per company per 90 days (tune); a second role at the same company inside that window is logged, not sent.
- **Channel:** both. Email through PlusVibe, 3 emails (tune); LinkedIn touches manually from the sender profile (no LinkedIn tool chosen).
- **First batch:** every triggered account, which is small by design (measured floor: 4 accounts in the first-month sample), so no separate ramp is needed beyond inbox health.
- **Companion workflow:** W2 (CBN circular exposure by register category) reuses the same register list and gives volume this workflow lacks.

---

## Approval record
Approved by the owner on 2026-11-13:
- Gate 1, after the signals table: the six signals and the trigger rule; the deviation that any register match counts, including foreign IMTOs; the six "Trusted by" logo companies stay excluded until cleared; generic engineering and generic finance titles do not fire.
- Gate 2, after the angle matrix: the 8 cells (six fire, C7 and C8 do not); the claim assignments, with naira collections (F13) only in C2 and F12 and F13 absent from C1, C3, C4, C5 and C6; C6 is kept.
- Sections 6 and 7 were built at the owner's request after gate 2 and approved with the save.

Still untested and not blocking copy: domain lookup by company name, per-company Apollo lookup, and the Clay, n8n, PlusVibe and HubSpot connections. Copy is written by `/campaign-copy`, which verifies this file's status and checklist first.

---

## Copy

Register: signal play. Channel: email and LinkedIn. Approved by the owner on 2026-11-13 after a persona review and human test (Email 1 was revised from its first approved version). Written from the approved angles above, using only `context/messaging/facts.md` claims F1 to F13 (quoted exactly) and the variables in section 6. The six cells are exhaustive, so no dynamic line has a fallback. No social proof line: facts.md authorises no customer name. No PS. Nothing here is a sequencer export; run Phase 3 of `/campaign-copy` when one is needed.

**Open items (not applied, need the owner):**
1. F12 and F13 read like API documentation. Proposed wording: F12 "You can lock an institutional exchange rate for a foreign currency amount, with a 60-second validity countdown." and F13 "You can collect Nigerian Naira (NGN) locally using dedicated NUBAN virtual accounts." Until approved, C2 Email 2 uses the verbatim claims.
2. C5 and C6 recipients are commercial leads, and F1 ("endpoint", "integrate separately") is engineer language. Proposed spec change: C5 and C6 use F2 and F5 and drop F1. Until approved, C5 Email 1 and C6 Email 2 use F1.
3. Sender identity: `{{sender_name}}`, `{{sender_title}}` and `{{signature}}` are unfilled. Recommended: the signature carries a name, a title and "Tabs"; the DMs go from a real profile.

### Email 1 (day 0, new thread)

**Subject (spintax):** `{{company_name}} + {one endpoint|africa payouts|payments in africa}`

**Body line map:** `{{first_name}},` then static L1 `{{e1l1}}`, dynamic L2 `{{e1l2}}`, static L3 (value prop), dynamic L4 `{{e1l3}}`, static CTA, `{{signature}}`.

**Static L1 `{{e1l1}}` (all cells):** {{company_name}} is hiring for the {{role_title}} role in {{role_location}}.

**Dynamic L2 `{{e1l2}}`** (a hedged guess, one sentence per cell, no spintax):
- + CELL C1 (ENG_PRODUCT and payment term): That probably means more markets to integrate.
- + CELL C2 (FIN_OPS and payment term): I'd guess the payments operations side is growing.
- + CELL C3 (COMPLIANCE and payment term): That could mean payment checks are getting more attention.
- + CELL C4 (COMPLIANCE, no payment term): Risk work may be growing.
- + CELL C5 (PARTNERSHIPS_BD and payment term): That usually points to new payment partners for new markets.
- + CELL C6 (PARTNERSHIPS_BD, no payment term): My guess is new markets or partners are in the plan.
- FALLBACK: none (the six cells cover every lead by construction; C7 and C8 do not send).

**Static L3 (value prop, no spintax):** Tabs is a cross-border payments platform that moves money into and out of Africa.

**Dynamic L4 `{{e1l3}}`** (the approved claim, quoted exactly):
- + CELL C1: One endpoint per market you were going to integrate separately. (F1)
- + CELL C2: One ledger where every local currency settles into your preferred currency. (F8)
- + CELL C3: KYB, screening and transaction monitoring run inside the payment flow, with audit trails included. (F9)
- + CELL C4: Account names are verified on the rail before money moves. (F4)
- + CELL C5: One endpoint per market you were going to integrate separately. (F1)
- + CELL C6: Start with one market. Keep the same integration. (F2)
- FALLBACK: none (exhaustive).

**Static CTA (spintax):** `{Relevant?|Worth a conversation?|Is that on your radar?}`

### Email 2 (day 3, same thread, subject "Re: <Email 1 subject>")

**Body line map:** `{{first_name}},` then dynamic L1 `{{e2l1}}`, dynamic L2 `{{e2l2}}`, static CTA, `{{signature}}`. No re-introduction of Tabs; each cell's second approved claim.

**Dynamic L1 `{{e2l1}}`** (a hedge, one sentence per cell, no spintax):
- + CELL C1: I wonder which market goes first.
- + CELL C2: More than one currency is probably involved.
- + CELL C3: My guess is payment checks are part of the brief.
- + CELL C4: I'd guess the open question is where checks sit in a payment.
- + CELL C5: The first partner market probably matters most.
- + CELL C6: I wonder which market or partner comes first.
- FALLBACK: none (exhaustive).

**Dynamic L2 `{{e2l2}}`** (new claim, quoted exactly):
- + CELL C1: Start with one market. Keep the same integration. (F2)
- + CELL C2: Lock in an institutional exchange rate for a foreign currency amount with a 60-second validity countdown. Collect Nigerian Naira (NGN) locally using dedicated NUBAN virtual accounts. (F12, F13)
- + CELL C3: Account names are verified on the rail before money moves. (F4)
- + CELL C4: KYB, screening and transaction monitoring run inside the payment flow, with audit trails included. (F9)
- + CELL C5: Start with one market. Keep the same integration. (F2)
- + CELL C6: One endpoint per market you were going to integrate separately. (F1)
- FALLBACK: none (exhaustive).

**Static CTA (spintax):** `{Does that fit?|Would that help?|Worth a closer look?}`

### Email 3 (day 10, same thread, static)

Body: `{{first_name}},` then: `{This is my last note|I'll leave it there}.` If this belongs with someone else at {{company_name}}, who should I ask? Then `{{signature}}`. No claim; the one new thing is the referral ask.

### LinkedIn (2 DMs, no DM 3)

- **Connection request:** empty (no note), sent 1 to 2 days after Email 1.
- **DM 1 (1 to 2 days after acceptance; dynamic, one question per cell):**
  - + CELL C1: {{first_name}}, is the {{role_title}} role more about new markets or existing ones?
  - + CELL C2: {{first_name}}, is the {{role_title}} role mostly settlement or reconciliation work?
  - + CELL C3: {{first_name}}, is the {{role_title}} role mostly about payments or the wider business?
  - + CELL C4: {{first_name}}, is the {{role_title}} role more about payments or other products?
  - + CELL C5: {{first_name}}, which market is the {{role_title}} role mainly for?
  - + CELL C6: {{first_name}}, is the {{role_title}} role about a new market or a new partner?
  - FALLBACK: none (exhaustive).
- **DM 2 (3 to 5 days after DM 1, static, spintax):** Asking because Tabs is a cross-border payments platform that moves money into and out of Africa. `{Happy to explain|Glad to explain}` how it works `{if that helps|if useful}`.
- **Coordination:** if the recipient replies on one channel, pause the other.

### Assembled sample (cell C6, from a measured posting; the first name comes from Apollo)

**Email 1.** Subject: taptap send + one endpoint

{{first_name}},

Taptap Send is hiring for the Head of Partnerships (Africa) role in Lagos.

My guess is new markets or partners are in the plan.

Tabs is a cross-border payments platform that moves money into and out of Africa.

Start with one market. Keep the same integration.

Relevant?

{{signature}}

**Email 2** (Re: taptap send + one endpoint)

{{first_name}},

I wonder which market or partner comes first.

One endpoint per market you were going to integrate separately.

Would that help?

{{signature}}

**Email 3** (same thread)

{{first_name}},

This is my last note. If this belongs with someone else at Taptap Send, who should I ask?

{{signature}}

**LinkedIn.** Empty connection request, then DM 1: "{{first_name}}, is the Head of Partnerships (Africa) role about a new market or a new partner?" Then, 3 to 5 days later, DM 2: "Asking because Tabs is a cross-border payments platform that moves money into and out of Africa. Happy to explain how it works if that helps."
