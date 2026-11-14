# Campaign strategy: Tabs Global

Generated 2026-11-13 with the campaign-strategy skill from `CLAUDE.md`, everything in `context/` (icp, personas, signal-matrix v3, positioning, messaging and facts, research, case-studies) and the Mother Intent Catalog in `knowledge-base/playbooks/workflow-anatomy.md`. Work in progress for a strategy session, not a final deliverable. Nothing here is approved for sending. Any claim in copy must come from `context/messaging/facts.md`: claims F1 to F13 and the value-prop line were approved by the repo owner on 2026-11-13 (see "Approved claims by campaign" below); the CTA and sender fields are still placeholders, and claim P3 is proposed only.

Tags: [icp], [personas], [matrix], [facts], [market], [competitors], [customers], [signals] = the file in context/ or context/docs/research/. INFERRED = my reading, not a source statement. PROXY = evidence from Verto or WeWire, the incumbents used as stand-ins because Tabs has no customers or case studies on record. Volume figures are estimates from the data pulled on 2026-11-13 and are labelled as such; "Not measured" means no data yet.

**Decisions already made by the owner (2026-11-13):** segment A (CBN-registered operators and Nigerian cross-border fintechs) is the first segment; D (African-HQ platforms, marketplaces, brokers, exchanges) is the second test. [matrix]

---

## Customer Discovery Analysis

**Tabs Global's own case studies reviewed: none exist.** The site, docs and terms contain no case study, testimonial or named customer. The six homepage logos (Hercle, Nomba, Currency Solutions, Paystack, Grey, Sterling) are not labelled as customers, so no campaign below may cite them. [customers], [facts]

**PROXY case studies (Verto and WeWire), used only to learn who buys this kind of product:**
| Company | Whose | Industry | Size | Problem | Result | Source |
|---|---|---|---|---|---|---|
| Triply | Verto | Travel platform for agencies in Africa | Not stated | Multi-day payments, several accounts, inconsistent rates | Atlas API: virtual accounts in "over 25 currencies", conversion, payouts; no numbers | https://verto.co/about-us/media-and-events/customer-stories/triply-customer-success-story/ |
| Cowrywise | Verto | Digital wealth platform, Lagos | Not stated | Low-cost FX to fund offshore assets; payouts to overseas brokers | Automated payments; no numbers | https://verto.co/about-us/media-and-events/customer-stories/cowrywise_verto_unlocking_global_investment_opportunities/ |
| Target Mart | Verto | Beauty and FMCG distribution, Kenya | Not stated | Bank forex rates, hidden fees, daily caps, slow documentation | Faster, cheaper supplier payments; no numbers | https://www.casestudies.com/company/verto-fx/case-study/unlocking-commercial-growth-through-optimised-cross-border-payment-operations |
| Start OA | WeWire | Services | Not stated | Not stated | Rates "more competitive than most platforms" (testimonial) | https://www.wewire.com/global-businesses |
Verto's homepage also names d.local, Lemfi, Paystack, MTN, IHS, Sun King and Target Mart; TechCrunch names Jumia, Chipper Cash, Taptap Send, Yoco and Interswitch. [customers]

**Patterns:**
- Industries: fintech and remittance apps (Lemfi, Chipper Cash, Taptap Send, d.local), software platforms (Triply, Cowrywise), a trade distributor (Target Mart), telecoms and infrastructure groups (MTN, IHS).
- Sizes: startup to large group; per-customer size is Not found.
- Titles at those customers: CEO, CTO, Commercial Director, Managing Director, Partner.
- Problems: bank FX cost and caps, slow documentation, multi-day settlement, needing one integration for accounts, conversion and payouts.

**Targeting recommendation (challenging the given ICP):**
- Remittance and cross-border fintech apps are buyers of payout rails, not exclusions; only providers selling the same B2B product are excluded. This corrects an earlier assumption. [matrix]
- Segment D (platforms) deserves a real test: three of Verto's four named stories are platforms, not payment firms.
- Segments B (trade) and E (foreign-currency accounts) have proxy pain but no data source, so no campaign below depends on them.

**Best lookalike seeds today:** none for Tabs. PROXY seeds only: Cowrywise, Triply, Lemfi, d.local. Tabs' own logos become seeds only if confirmed as customers. [customers]

## Data checks run today (cost $0.00935 on treg)
- **Jobs searches (6 earlier today, plus 1 new, $0.00045 each).** "Payment Partnerships Manager (Africa)" roles are a precise hit (FxPro x2, Luno, Nilos). "payments engineer" returns mostly generic engineers. A query naming incumbent rails (Flutterwave, Paystack, Fincra, Kora, Verto) returned the same generic engineering roles; job cards show titles only, so a named rail cannot be seen, and that signal is UNVERIFIED. [matrix]
- **Lookalike test (treg `companies.similar`, $0.0089, capped at $0.02).** Seed cowrywise.com returned 7 companies, mostly UK and US wealth and investment firms (for example Killik & Co, Save & Invest), none a fit for Tabs. Lookalike data is weak without a confirmed seed. [new]
- **CBN registers (free).** PSP register 279, IMTO register 108; first join sample matched Belyfted Limited. [matrix]
- **Excluded by rule:** G2, Capterra and Trustpilot are not used as campaign data (the skill bars them); the earlier incumbent-complaints signal (X1) stays message research only and is not a campaign here.

---

## Ranking: signal strength and how easy the data is to get

Signal strength (S) and data ease (D) are scored 1 to 5 by me from the evidence above; rank = S + D, ties broken by S. Tier follows the skill's five factors.

| Rank | # | Campaign | Tier | S | D | Score | Volume per month (estimate) | Difficulty |
|---|---|---|---|---|---|---|---|---|
| 1 | 4 | Cross-border payments hiring at registered operators (W1) | 1 | 4 | 4 | 8 | about 4 to 10 triggered accounts (measured floor: 4 in a first-month sample) | Medium |
| 2 | 5 | Payment Partnerships (Africa) roles at platforms and brokers (W3) | 1 | 4 | 4 | 8 | 5 to 10 accounts | Low |
| 3 | 3 | CBN circular deadline exposure (W2) | 1 | 3 | 5 | 8 | up to 279, one-time list | Low |
| 4 | 6 | Africa roles outside Africa (W4) | 2 | 4 | 3 | 7 | 5 to 10 non-provider accounts | Medium |
| 5 | 18 | Golden 25: hand-checked top accounts | 2 | 4 | 3 | 7 | 25 by design | Medium |
| 6 | 2 | IMTO naira settlement exposure (W5) | 2 | 3 | 4 | 7 | up to 108, one-time list | Low |
| 7 | 7 | Africa market-entry hires at exchanges and brokers | 2 | 3 | 4 | 7 | 3 to 8 accounts | Low |
| 8 | 8 | Compliance and MLRO hires | 2 | 3 | 4 | 7 | 2 to 6 accounts | Low |
| 9 | 14 | New head of payments, treasury or partnerships | 2 | 4 | 2 | 6 | Not measured | High |
| 10 | 15 | Global payroll and EOR platforms paying Africa | 3 | 3 | 3 | 6 | 1 to 3 accounts | Medium |
| 11 | 1 | Creative use cases, sent to the register list | 2 | 2 | 4 | 6 | base list size | Low |
| 12 | 9 | Hiring velocity at Nigerian fintechs | 3 | 2 | 4 | 6 | 10 to 20 accounts | Low |
| 13 | 13 | Funding events at Nigerian cross-border fintechs | 2 | 3 | 2 | 5 | 2 to 4 accounts | Medium |
| 14 | 16 | Lookalike of proxy customers | 3 | 3 | 2 | 5 | Not usable yet | High |
| 15 | 12 | Creative (non-ICP): advisers who serve the ICP | 3 | 2 | 3 | 5 | 10 to 30 firms, one-time | Medium |
| 16 | 17 | Creative (non-ICP): investors backing African payments | 3 | 2 | 3 | 5 | about 10 firms, one-time | Medium |
| 17 | 11 | Job posts that name an incumbent rail | 3 | 3 | 1 | 4 | Not measurable | High |
| 18 | 10 | Engagers on posts about the CBN circular | 3 | 2 | 2 | 4 | Not measured | High |
| 19 | 19 | Event speakers and attendees | 3 | 2 | 2 | 4 | Not measured | High |

The "#" column is the order in the broad-to-niche table below.

---

## Campaign ideas (broadest to most niche)

Required types are marked: **Creative Ideas** (#1), **New Hire** (#14), **Lookalike** (#16), **Creative (non-ICP)** (#12 and #17), **Golden ICP** (#18). Three Creative Stretch ideas are #10, #11 and #15.

| # | Campaign | Level | Mother Intent | Tier | Segment and persona | Signal and data source | AI strategy | Angle (value prop) | Volume per month | Difficulty |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Creative use cases (**Creative Ideas**) | Broad | Niche-specific play | Tier 2: no timing signal, fast build | A first, then D. Champion (product or engineering) | Base list: CBN registers (387 names, free) plus company website text | Read the prospect's site and write 3 specific uses (paying overseas partners, collecting in naira, holding USD) as questions, not claims | Save time: one endpoint per market | Base list size, not a monthly flow | Low: free list, site parsing |
| 2 | IMTO naira settlement exposure (W5) | Focused | Regulatory changes | Tier 2: finite list, already in force, circular unread | A. Economic buyer (finance, ops), compliance influencer | IMTO register (108, https://www.cbn.gov.ng/PaymentsSystem/InternationalMoneyTransferOperators.html); directive dated 2026-03-24, effective 2026-05-01 (news, text unread) | Light: register category and operator name only | Mitigate risk: settle recipients in naira, one rail | Up to 108, one-time | Low |
| 3 | CBN circular deadline exposure (W2) | Focused | Regulatory changes | Tier 1: free finite list, dated hook, about 7 weeks to 2026-12-31 | A by register category (PSSP 124, PTSP 47, super agents 61, MMO 17, switching 19, schemes 8). Compliance influencer, economic buyer | PSP register (279) plus circular of 2026-06-15: market structure by 2026-12-31, data localisation by 2027-01-01 (scope per BusinessDay; circular text unread) | Match category to the scope line the circular names | Mitigate risk: situation only, no claim that Tabs solves localisation (Tabs' status is Not found) | Up to 279, spread over about 7 weeks | Low |
| 4 | Cross-border payments hiring at registered operators (W1) | Focused | Hiring specific roles | Tier 1: strong signal, free list joins weekly jobs data | A. Champion (head of product or payments engineering), economic buyer | LinkedIn public jobs, queries `cross-border payments`, `payouts`, `settlement`, Nigeria, posted within a month, joined to the registers by company name; treg `crawl4ai.linkedin.search.jobs` $0.00045 per call. Measured 2026-11-13: of 66 job employers, 10 matched the 354 register names, 4 would trigger after exclusions; no payment term in a title matched (see the W1 spec) | Pull the role title and what it implies about the corridor being built | Make more money: add corridors without a new integration each time | about 4 to 10 triggered accounts (measured floor: 4) | Medium: name matching, role-family routing |
| 5 | Payment Partnerships (Africa) roles (W3) | Focused | Hiring specific roles | Tier 1: precise title, cheap, fast build | D (African-HQ platforms, brokers, exchanges); some hits are non-African HQ and belong to C. Economic buyer (partnerships head), champion | LinkedIn jobs, query `Payment Partnerships Manager Africa`, Nigeria and Kenya. Seen 2026-11-13: FxPro (2 postings), Luno, Nilos; also OKX, OSL | Reference the role title and the market named in it | Make more money: local payout and collection rails for a new market | 5 to 10 accounts (INFERRED from the pulls) | Low; HQ check needed |
| 6 | Africa roles outside Africa (W4) | Focused | Hiring offshore | Tier 2: strong signal, heavy provider noise | C (non-African HQ). Economic buyer, champion | LinkedIn jobs, `payments Africa expansion` in United States, `cross-border payments partnerships Africa` in United Kingdom. Seen: Taptap Send x4, Coins.ph, Remitly, Kredete; most other hits are providers | Name the role and the African market | Make more money: start with one market, keep the same integration | 5 to 10 non-provider accounts (INFERRED) | Medium: provider exclusion list |
| 7 | Africa market-entry hires at exchanges and brokers | Niche | Hiring specific roles | Tier 2: new-market signal, small list | D and C. Economic buyer (country manager, growth head) | LinkedIn jobs, `Country Manager Africa`, `Business Development Nigeria`. Seen: OSL Country Manager (Africa), FxPro Business Development Manager (Nigeria), Caliza BD Lead (Nigeria), a stealth P2P marketplace Head of Growth (Africa) | Cite the new-market role, ask about payout and funding rails | Make more money: launch a market without building rails | 3 to 8 accounts (INFERRED) | Low |
| 8 | Compliance and MLRO hires | Niche | Hiring specific roles | Tier 2: ties to circular season | A and D. Compliance influencer | LinkedIn jobs, `Head of Compliance MLRO`, `Regulatory Compliance Manager`, Nigeria. Seen: OKX Head of Compliance and MLRO (2026-10-30), CredPal Regulatory Compliance Manager | Reference the compliance role, not the company's problems | Mitigate risk: screening and name checks before money moves (homepage FAQ wording) | 2 to 6 accounts (INFERRED) | Low |
| 9 | Hiring velocity at Nigerian fintechs | Focused | Companies in hypergrowth (hiring velocity) | Tier 3: signal is generic hiring, weak tie to payments | A and D. Champion (CTO, head of engineering) | Count open roles per company from jobs pulls (Moniepoint, Paystack, PalmPay, M-KOPA, Cavista, Shuttlers each showed 2 or more). treg `blitzapi.jobs.company` $0.001 per record | Summarise what the engineering roles imply | Save time | 10 to 20 accounts (INFERRED) | Low; low relevance |
| 10 | Engagers on posts about the CBN circular | Niche | LinkedIn content engagement | Tier 3: unproven, high effort | A and D. Compliance influencer, finance heads | Reactions and comments on posts such as "The CBN's June 15 circular deserves a closer read than it's getting" (LinkedIn post by Mary Adesanya, seen in search results); treg `linkedin.post.reactions` and `linkedin.post.comments`, prices not checked | Reference the topic they engaged with, not the person's activity | Mitigate risk | Not measured | High: price, consent and relevance unchecked |
| 11 | Job posts that name an incumbent rail | Niche | Competitor customers | Tier 3: cannot be verified from job cards | A and D. Champion | LinkedIn job descriptions that mention Flutterwave, Paystack, Fincra, Kora or Verto. Tested 2026-11-13: cards show titles only, so the rail named is not visible | Would ask about adding a second rail; never name a competitor in copy | Save money, mitigate risk (INFERRED) | Not measurable | High: needs a source with job description text |
| 12 | Advisers who serve the ICP (**Creative (non-ICP)**) | Niche | Regulatory changes (referral audience) | Tier 3: partner channel, slow payoff | Law, tax and advisory firms that publish on the CBN circular and Tax Acts: seen Aluko & Oyebode, Banwo & Ighodalo, SCP, PwC Nigeria, KPMG Nigeria, EY. Partner or head of fintech practice | Public articles and PDFs on the 2026 circulars and tax acts (web search, free) | Reference the specific article and how their clients' cross-border flows relate | Make more money by referral, not a sale; no commission promised | 10 to 30 firms, one-time (INFERRED) | Medium: partner terms undecided |
| 13 | Funding events at Nigerian cross-border fintechs | Niche | Companies fundraising | Tier 2: real events, coverage unknown | A. CEO or founder (small firms) | Press: Pouchers $500,000 pre-seed (August 2026), Daya $2.4M pre-seed, Accrue $1.58M seed, Raenest $11M Series A (February 2025). WebSearch free; Crunchbase via Clay not confirmed | Congratulate and ask which corridor the money funds | Make more money: scale corridors | 2 to 4 accounts (INFERRED from 2025 and 2026 press) | Medium: manual news until a feed exists |
| 14 | New head of payments, treasury or partnerships (**New Hire**) | Niche | New leadership (past 90 and 180 days) | Tier 2: strong signal, weak data | A and D. The new leader is the economic buyer | Apollo free people search finds titles but no start date; profile lookup with `brightdata.linkedin.user.profile` ($0.0015, not tested). Apollo returned 2,708 loose Nigerian matches for treasury, payments, finance titles across all industries (earlier today) | Pull start date and previous company; "you may be reviewing providers in your first months" | Save time: a fast win in the first 90 days | Not measured; start-date filter untested | High: tenure data |
| 15 | Global payroll and EOR platforms paying Africa | Niche | Niche-specific play | Tier 3: tiny list | D. Payroll operations head, partnerships | LinkedIn jobs `payroll specialist Africa`. Seen: RemotePass (Senior Payroll Specialist, Global, Egypt and Morocco listings, 2026-11-13) | Reference the African payroll roles | Save time: local payouts across markets | 1 to 3 accounts (INFERRED) | Medium |
| 16 | Lookalike of proxy customers (**Lookalike**) | Niche | Lookalike of customers | Tier 3: no Tabs customer to seed, test result poor | D and A. CTO, CEO | treg `companies.similar` ($0.0089 per call, up to about $0.70 uncapped across providers). Seed cowrywise.com returned 7 mostly UK and US wealth firms (test) | "A company like yours uses a rail like this": only names authorised in facts.md may appear, and none are | Save time | Not usable yet | High: needs a confirmed Tabs customer as seed |
| 17 | Investors backing African payments (**Creative (non-ICP)**) | Niche | Niche-specific play | Tier 3: portfolio intros, slow | Funds that backed the category: Quona Capital, MEVP, QED Investors, TMT Investments, Y Combinator (seen in Verto and Raenest funding coverage). Partner, platform lead | Fund and portfolio pages (public) | Reference a portfolio company's market entry | Make more money by introductions | About 10 firms, one-time (INFERRED) | Medium: relationship-led |
| 18 | Golden 25: hand-checked top accounts (**Golden ICP**) | Niche | Niche-specific play | Tier 2: high quality, manual | A. Champion and economic buyer, named | Intersection of register membership, a live cross-border role and the circular category; a rep spends 10 minutes per account (role, corridor, category) | AI drafts one situational line per account from the role and register category; human checks it | Mitigate risk and make more money | 25 by design | Medium: manual review |
| 19 | Event speakers and attendees | Niche | Companies attending an event | Tier 3: dates and lists Not found | A and D. Heads of payments and partnerships | Public speaker pages for events such as the Finance Magnates Africa Summit (Kora presented there per EU-Africa Chamber coverage); Apify or a page scraper; dates Not found | Reference the session topic | Make more money | Not measured | High |

### Campaign overviews (hook, personalization, call to action, proof)
Proof for every campaign: none that names a customer. Use only wording approved in facts.md (claim map below); the CTA is not yet decided (Tabs' own: "Get a demo", "Read the docs", "Talk to us").
- **#1 Creative use cases:** open "I had an idea for {{company_name}}", then three question-style uses from their own site. Differs from #4 by using no timing signal. CTA: ask which one is worth a look.
- **#2 IMTO naira settlement:** a short situation line about paying recipients in naira under the 2026 directive, then one question about their settlement setup. Never state what the circular requires beyond its date and scope.
- **#3 CBN circular exposure:** one line on the two dates and the operator's register category, then ask who owns the work. No claim that Tabs fixes localisation.
- **#4 Cross-border hiring (W1):** reference the exact role ("I saw you are hiring a {{role_title}}") and the corridor it implies; angle by persona from the matrix. CTA: a short call or the docs.
- **#5 Payment Partnerships roles (W3):** reference the role and market ("Payment Partnerships Manager (Africa)"); lead with one integration for local payouts and collections.
- **#6 Africa roles abroad (W4):** reference the Africa role; "start with one market, keep the same integration".
- **#7 Market-entry hires:** reference the Country Manager or BD role; ask how payouts and funding will work in the new market.
- **#8 Compliance hires:** reference the compliance role; angle is screening and recipient name checks inside the payment flow (homepage FAQ).
- **#9 Hiring velocity:** reference the engineering hiring pace; low relevance, so test only if #4 and #5 run dry.
- **#10 Circular post engagers:** one line tied to the topic; do not mention the post author or the engagement itself.
- **#11 Incumbent-rail posts:** do not build until a source shows job description text.
- **#12 Advisers:** reference their article; propose a conversation about clients' cross-border flows; no referral terms until decided.
- **#13 Funding events:** congratulate, ask which corridor the money funds.
- **#14 New leader:** reference role start and previous company once tenure data exists.
- **#15 Payroll platforms:** reference the African payroll roles.
- **#16 Lookalike:** blocked until a Tabs customer exists or a logo is confirmed.
- **#17 Investors:** ask for portfolio introductions to teams entering African markets.
- **#18 Golden 25:** two sentences written for one named person, from a role the company posted.
- **#19 Events:** reference the session topic.

---

## Approved claims by campaign

Source: `context/messaging/facts.md`, approved by the repo owner on 2026-11-13 (F1 to F13). Quote the phrasing exactly and respect each claim's "use only" limit. **VP** = the value-prop line: "Tabs is a cross-border payments platform that moves money into and out of Africa." (alternate: "Tabs is the payment infrastructure for Africa.").

| ID | Approved phrasing (exact) | Use only |
|---|---|---|
| F1 | "One endpoint per market you were going to integrate separately." | As written |
| F2 | "Start with one market. Keep the same integration." | As written |
| F3 | "Instant · 24/7" | Local rails; never South Africa; no "fastest"; no "<5 min" |
| F4 | "Account names are verified on the rail before money moves." | As written |
| F5 | "African businesses can hold USD, EUR and GBP accounts with FX built in." | No rates, fees or country claims |
| F6 | "Signed, replayable" | Developer-facing copy only |
| F7 | "Tabs Global Limited is a financial technology company, not a bank." | Never call Tabs a bank |
| F8 | "One ledger where every local currency settles into your preferred currency." | No "instant" with it |
| F9 | "KYB, screening and transaction monitoring run inside the payment flow, with audit trails included." | No "licensed", no regulator or partner names, no claim about any CBN rule |
| F10 | "Every rail, no contract" | Only about the sandbox |
| F11 | "licensed banks and payment institutions that Tabs partners with" | Only if the prospect asks about licensing; never name a bank or regulator |
| F12 | "Lock in an institutional exchange rate for a foreign currency amount with a 60-second validity countdown." | Only the 60 seconds; no rate, margin or comparison |
| F13 | "Collect Nigerian Naira (NGN) locally using dedicated NUBAN virtual accounts." | Nigeria only; no other country; no speed claim with it |

| # | Campaign | Claims it may use | Off-limits for this campaign |
|---|---|---|---|
| 1 | Creative use cases | VP, F1, F2, F5, F8, F12, F13 | Fees, coverage lists, rates or margins |
| 2 | IMTO naira settlement | VP, F1, F8, F9, F13 | Stating what the directive requires beyond its date and scope; any claim that naira collection satisfies it |
| 3 | CBN circular exposure | VP, F7, F9 | Any claim that Tabs solves data localisation or market-structure rules (Tabs' status Not found); "licensed" |
| 4 | Cross-border hiring (W1) | VP, F1, F2, F4, F5, F6, F8, F9, F12, F13 | Fees, corridor lists, "fastest", rates or margins; routed per cell in the W1 spec |
| 5 | Payment Partnerships roles (W3) | VP, F1, F2, F3, F5, F12 | Country lists; South Africa with F3 |
| 6 | Africa roles outside Africa (W4) | VP, F2, F5, F8 | Country lists; fees |
| 7 | Market-entry hires | VP, F1, F2, F3 | Named markets, since the live list is unconfirmed |
| 8 | Compliance and MLRO hires | VP, F4, F7, F9, F11 (if asked) | Licence or regulator names; any rule-specific claim |
| 9 | Hiring velocity | VP, F1, F6 | Anything about the prospect's stack |
| 10 | Circular post engagers | VP, F9 | Mentioning the post author or the engagement |
| 11 | Incumbent-rail posts | None: not buildable | Naming any competitor |
| 12 | Advisers who serve the ICP | VP, F7, F9, F11 (if asked) | Referral terms or commission (undecided) |
| 13 | Funding events | VP, F1, F2 | Valuation or funding figures about Tabs |
| 14 | New leader | VP, F1, F8 | Pre-dating their role; any claim about their previous company |
| 15 | Payroll platforms | VP, F1, F3 | Payroll product claims (Tabs lists none) |
| 16 | Lookalike | None: blocked | Naming any customer; none is authorised |
| 17 | Investors | VP, F2 | Funding, valuation or customer claims |
| 18 | Golden 25 | By persona: champion F1, F6; economic buyer F5, F8; influencer F4, F9 | Everything in the "Numbers to keep fuzzy" list |
| 19 | Event speakers | VP, F1 | Event names or dates until confirmed |
| No-AI deadline note | Plain deadline note | VP, F9 | Same limits as #3 |
| No-AI sandbox invite | Sandbox invitation | VP, F10, F6, F1 | Any claim about what the sandbox covers beyond F10 |

**Always placeholders until filled:** `{{sender_name}}`, `{{sender_title}}`, `{{signature}}`, `{{cta}}`.
**Never in any campaign:** social-proof names or logos (none authorised), any number from "Numbers to keep fuzzy" (including "$100m+", "99.9%", "20+ currencies", "<5 min", the 0.01% fee), competitor names, price or fee comparisons, "bank" language for Tabs, proxy facts about Verto or WeWire.

**Angles that needed claims:** "collect naira" and "lock a quote for 60 seconds" were approved on 2026-11-13 as F13 and F12. P3 (corridor requirements) is still proposed and stays out of copy.

## No-AI campaigns
- **Plain deadline note to register operators.** Why it works without AI: the list is a public register and the hook is a published date, so a short static note can carry it. Core message: one line naming the two dates, one line asking who owns the work, one line offering the docs. Built from #3 with no per-row generation.
- **Sandbox invitation to developers.** Why it works: Tabs' own homepage says "Every rail, no contract" for the sandbox, which is a low-commitment ask for champions. Core message: one line on what the sandbox covers (from the docs), one link, one question. Built from #4 or #5 lists with static copy.

## Front-end offer suggestions
1. **Sandbox access** ("Every rail, no contract", homepage): the prospect tries a payout in the sandbox before any sales call. Rationale: the champion sees the product firsthand; the docs list payouts, FX quotes and webhooks.
2. **Corridor requirements check:** the docs list a "corridor requirements" endpoint; offer to send the requirements for the two or three corridors a prospect names. Rationale: concrete and free; needs Tabs to confirm which corridors are live.
3. **One-page CBN dates sheet:** the two deadlines and the register categories in scope, with sources. Rationale: useful to compliance and finance without a pitch; must not imply Tabs solves localisation, and the circular text should be read first. Needs to be written and approved.

---

## Recommendation: build #4 first (W1, cross-border payments hiring at registered operators)

**Why this one:**
- It is the first-ranked idea on signal strength and data ease (S4, D4) and it sits in segment A, which you chose to run first.
- Its list is free and finite (CBN registers, 387 names) and its trigger is a weekly jobs search at $0.00045 per call; a first sample already produced a real match (Belyfted Limited, a Full Stack Developer role in Lagos posted 2026-10-27).
- The build is shared: the same register scrape feeds #2 and #3, and the same jobs build feeds #5, #6, #7 and #8 with keyword swaps.
- It does not depend on facts we cannot confirm: the angle is situational ("you are hiring for X") and needs no customer proof.

**Risks to manage:** keyword noise (use `cross-border payments`, `payouts`, `settlement`; avoid `payments engineer` and treasury terms alone), name-matching between job posts and register names, and the provider exclusion list (Verto, WeWire, Nomba, Kora, Fincra and others). The email provider, LinkedIn tool and CTA are undecided, and Clay and n8n are not confirmed connected.

**Build second, in a time window:** #3 (circular exposure) reuses the register scrape and has a date; if it is going to run, it should send before 2026-12-31. Decide that when the W1 spec is approved. Segment D's first test is #5.

**Do not build yet:** #11 (cannot be verified), #16 (no seed), #14 (no tenure data), and anything on G2, Capterra or Trustpilot.

## What to do next
Run `/build-workflow-spec` on #4. It turns the idea into `output/campaigns/<workflow-slug>/workflow-spec.md` (signals, routing, an angle per cell). Then `/campaign-copy` writes the sequence from that approved spec.
