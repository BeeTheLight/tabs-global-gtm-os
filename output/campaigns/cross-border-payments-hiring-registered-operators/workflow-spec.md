# Workflow spec W1: Cross-border payments hiring at CBN-registered operators

**Status:** STRUCTURE-DRAFT 2026-11-13 · awaiting owner approval · copy blocked until the status reads STRUCTURE-APPROVED

Built with `/build-workflow-spec` from campaign-strategy idea #4 (`output/campaigns/campaign-strategy.md`), `context/icp/icp.md`, `personas.md`, `signal-matrix.md` v3, `context/messaging/facts.md` (claims F1 to F13 approved by the owner on 2026-11-13) and the measured data below. This file contains structure only. It has no copy: `/campaign-copy` writes narrative from the approved angles. Sections are tagged [ENGINE] (reusable) or [ICP] (the part that changes for another segment).

---

## 1. Mother Intent (Trigger) [ENGINE]
A CBN-registered payment operator has posted a role in the last 30 days for a function that touches payments (engineering or product, finance or operations, compliance, or partnerships and business development). Catalog intent: **Hiring specific roles** (`knowledge-base/playbooks/workflow-anatomy.md`).

## 2. Inclusion / Exclusion [ICP]

**Include**
- **ICP box (segment A, from icp.md and signal-matrix v3):** the company's normalized name matches an entry on the CBN PSP register (parsed on 2026-11-13: 246 entries) or the CBN IMTO register (108 entries). The register is the filter. Businesses only.
- **Deviation from the matrix, for approval:** the matrix defines A as "Nigeria-based". The IMTO register also lists foreign companies that hold a CBN licence (for example Taptap Send UK Limited and Remitly Inc.). This spec includes any register match, whatever its HQ, because the licence is the observable fact and the exclusivity rule in the matrix already says "on a register means A".
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
| C2 | S3 = FIN_OPS and S4 = true | The company is adding operations or finance capacity for payment flows (settlement, reconciliation, payments operations). Recipient: economic buyer | Money that settles into one ledger in the preferred currency, with naira collected locally and a locked quote before committing. Claims F8, F13, F12; F5 if foreign-currency accounts fit the role. Uses `{{role_title}}` |
| C3 | S3 = COMPLIANCE and S4 = true | The company is adding compliance capacity specifically for payments. Recipient: influencer | Screening and monitoring inside the payment flow with audit trails, and recipient names verified before money moves. Claims F9, F4. Uses `{{role_title}}`. No claim about any CBN rule |
| C4 | S3 = COMPLIANCE and S4 = false | The company is adding compliance, risk or fraud capacity; the title does not say payments. The role is the only evidence, so the angle cannot assume a payments focus. Recipient: influencer | Same meaning as C3 but anchored only on the role: checks run inside the payment flow (F9) and names are verified before money moves (F4). Must not say "your payments compliance". Uses `{{role_title}}` |
| C5 | S3 = PARTNERSHIPS_BD and S4 = true | The company is adding a payments partner or rail for new markets, for example a payment partnerships role for Africa. Recipient: economic buyer | One integration for the markets they are adding: one endpoint per market, start with one market. Claims F1, F2. Uses `{{role_title}}` |
| C6 | S3 = PARTNERSHIPS_BD and S4 = false | The company is expanding commercially (partnerships, expansion, country management); no evidence about payment rails. Recipient: economic buyer | Start with one market and keep the same integration (F2); naira collected locally (F13) only if the role names Nigeria. Must not assume a payments gap. Uses `{{role_title}}`, `{{role_location}}` |
| C7 | S3 = ENG_PRODUCT and S4 = false | A generic engineering hire at a register operator; the posting says nothing about payments | **No send.** Logged for the weekly review only, so we can test later whether it deserves a route |
| C8 | S3 = FIN_OPS and S4 = false | A generic finance or operations hire | **No send.** Logged for the weekly review only |

**Branch coverage.** Every firing cell has a job posting, so `{{role_title}}` and `{{role_location}}` exist in C1 to C6. C4 and C6 have no payment term in the title, so their angles do not mention payments in the role. Claims about naira (F13) appear only where the role location or title names Nigeria. No cell uses headcount, funding, corridors, volumes or the job description, because none is delivered.

**Niche-native test.** Every firing angle is anchored on a specific role posted by a CBN-registered operator in the last 30 days; no other company category could send it unchanged.

## 6. Variables contract [ENGINE]

| Variable | Source field | Exists in branches |
|---|---|---|
| `{{first_name}}` | Apollo people search, recipient first name | C1 to C6 (no send if the recipient is not found) |
| `{{company_name}}` | Register entry, display form with legal suffix removed | C1 to C6 |
| `{{role_title}}` | Job card title | C1 to C6 |
| `{{role_location}}` | Job card location | C1 to C6 |
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

## Open items for the owner before this can read STRUCTURE-APPROVED
1. Approve the signals table (section 4) and the angle matrix (section 5); these two drive everything.
2. Approve the deviation in section 2 (any register match counts, including foreign IMTOs).
3. Decide whether the "Trusted by" logo companies stay excluded until confirmed (recommended).
4. Confirm that C7 and C8 (generic engineering and finance titles) should not send.
5. Untested pieces: domain lookup by company name, per-company Apollo lookup, and Clay and n8n connections.
