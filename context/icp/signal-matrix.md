# Signal Matrix: Tabs Global (draft v3, rebuilt 2026-11-13 from the refreshed research)

Work in progress for a strategy session, not a final deliverable. Rebuilt from scratch with the signal-matrix skill after the research refresh, using `context/icp/icp.md`, `context/icp/personas.md`, `context/positioning/`, `context/docs/research/` and the playbooks `signal-matrix-framework.md` and `workflow-anatomy.md`. This replaces the earlier version.

Tags: [company], [customers], [competitors], [market], [signals], [voice] = research file in `context/docs/research/`. INFERRED = my reading, not a source statement. **PROXY** = evidence from Verto or WeWire, the incumbents used as stand-ins because Tabs has no customers or case studies on record; it shows what a Verto-like company's buyers look like, not who buys from Tabs. "Seen in test" = from a tool call or page fetch made on 2026-11-13, listed under Evidence.

**What Tabs sells.** Tabs Connect: an API for cross-border payouts, local collections, USD, EUR and GBP accounts and FX for businesses moving money into and out of Africa. Single product, businesses only, no confirmed customers, no published pricing, 2-10 employees, founded 2026. [company], [customers]
**Competitors and providers (exclude as targets).** Verto, WeWire, Nomba, Kora, Fincra, Flutterwave, Yellow Card, Thunes, Raenest, Grey, Afriex, Cleva, WorldFirst, and in the jobs data also PingPong Payments, XTransfer, Duplo, Airwallex, Wise, Payoneer. [competitors], jobs pulls below
**Data reality.** Africa has no Crunchbase-grade coverage, but three things work: LinkedIn public jobs return Nigerian, Kenyan and Egyptian data; Apollo free people search returns African titles; and the CBN publishes licensed-operator registers as free HTML tables. Clay and n8n are not confirmed connected; treg is. [signals]
**Single-product company**, so Matrix 1 has no product columns; the angle changes per cell.

## What changed from the previous matrix
- Segment list now has five rows (A, D, C, B, E) with an exclusivity rule between them; D and E are from proxy evidence.
- Remittance apps (Lemfi, Taptap Send, Chipper Cash) are Verto customers, so they are PROXY buyers of payout rails, not exclusions. Only providers that sell the same B2B product are excluded. This corrects the old line that treated consumer-remittance apps as exclusions.
- D1 was run for real: "Payment Partnerships Manager (Africa)" roles at FxPro, Luno and others are a precise, repeatable hit (VERIFIED, PARTIAL).
- A2 and A3 merged; "payments engineer" returned mostly generic engineers, so keywords are tightened.
- A1 now has re-checked register counts (PSP 279, IMTO 108) and a scope list for the 2026-06-15 CBN circular from BusinessDay, and a first A1 x A2 join example.
- A7 (competitor launches) and X1 (incumbent complaints) are message research, not list sources.

---

## Phase 1: who could buy this (wide net, before filtering)

| Buyer group | Why they might need Tabs | Evidence |
|---|---|---|
| Nigerian PSPs, IMTOs, remittance and cross-border fintechs | Pay out abroad or in naira, hold foreign currency, need a rail partner | Nomba launched a payout API for "cross-border payment operators, remittance platforms, and fintechs" (2026-03-18); PROXY: Lemfi, Taptap Send, Chipper Cash, d.local are Verto customers [competitors], [customers] |
| Platforms, marketplaces, brokers, exchanges, payroll and wealth platforms with African payouts or collections | One API for virtual accounts, FX and payouts | PROXY: Triply, Cowrywise (Verto stories) [customers]; seen hiring: FxPro, Luno, RemotePass |
| Non-African businesses paying into Africa | Hold USD, EUR, GBP and pay out on local rails | LinkedIn About "global businesses"; PROXY: Verto US-to-Africa USD accounts [company], [competitors] |
| African importers, exporters, distributors | Supplier payments, bank FX cost and caps | PROXY: Target Mart (Kenya) [customers]; FX Manual [market] |
| African exporters and services firms | Foreign-currency receiving accounts | Press on US bank closures; Tabs FAQ on USD, EUR, GBP accounts [market], [company] |
| Banks, large corporates, NGOs, freelancers, consumers | Different product or not served | Tabs serves businesses only; banks not researched [company] |

## Matrix 1: Segments x Personas

**Axis choice (INFERRED reasoning, not confirmed with the user).** Rows are the buyer's business model, because that decides how we find them (register, jobs, geography) and what they do with Tabs. Columns are the three INFERRED personas, because the angle changes by role. "Existing solution" (bank, a provider such as Verto, or in-house) would be a better axis for displacement versus greenfield messaging but is not observable, so it stays a discovery question per call, not an axis. [framework rule: observable]

**Exclusivity rule.** A company on the CBN PSP or IMTO register is A. Otherwise a non-African HQ is C. Otherwise an African-HQ platform, marketplace, broker, exchange or software business is D. Otherwise a trade business is B and a foreign-currency-account seeker is E. Provider-competitors are excluded everywhere.

| Segment | Champion (engineering or product) | Economic buyer (finance or ops) | Influencer (compliance or treasury) |
|---|---|---|---|
| **A. CBN-registered operators and Nigerian cross-border fintechs** | "As you add corridors, one endpoint per market means no new integration each time." (Pillar 1) | "Collect naira, pay out in USD, EUR or GBP, and lock a quote for 60 seconds before you commit." (Pillars 2, 3) | "Screening and recipient name checks run before money moves, ahead of the CBN dates at the end of 2026." (Pillar 4, dates in [market]) |
| **D. African-HQ platforms, marketplaces, brokers, exchanges (PROXY evidence)** | "One integration for virtual accounts, conversion and payouts, instead of one per market." (Pillar 1; PROXY: Triply used Verto Atlas this way) | "Predictable FX and settlement for the money your customers move." (Pillars 2, 3) | "KYB, screening and monitoring run inside the payment flow." (Pillar 4, homepage FAQ wording) |
| **C. Non-African businesses paying into Africa** | "Start with one market. Keep the same integration." (Pillar 1) | "Hold USD, EUR or GBP and pay out on local rails from one balance." (Pillar 2) | "KYB and screening on the recipient side." (Pillar 4) |
| **B. African trade businesses** | INFERRED: usually no engineer in this role; merge with the economic buyer. | "Supplier payments from one balance, with a locked FX quote." (Pillars 2, 3). Link to the FX Manual 4th edition is INFERRED | Not found. Pillar 4 basics only. Do not claim FX Manual documentation support. |
| **E. African firms needing foreign-currency accounts (PROXY evidence)** | INFERRED: usually no engineer; skip. | "Hold USD, EUR and GBP and get paid by foreign customers, with FX built in." (Pillar 2, Tabs FAQ wording) | Not found. Pillar 4 basics only. |

Pillars are from messaging.md. Persona titles seen at proxy customers: CEO (Triply), CTO (Cowrywise), Commercial Director (Target Mart). [customers]

### Target definitions (observable, filterable) and company examples
Only real names seen in a source. "Fit NOT verified" means the name appeared in a tool result, not that it fits.

| Segment | Definition (filterable) | Company examples |
|---|---|---|
| A | Entity listed on the CBN PSP register (279: Card/Payment Schemes 8, Mobile Money 17, Switching and Processing 19, Payment Solution Services 232, Payments Service Holding 1, Terminal Service Aggregator 2) or the IMTO register (108); Nigeria-based; pays out or collects across borders. The register is the filter. [CBN PSP and IMTO pages] | On the IMTO register (first 25 of 108 read): Afriex Inc (a competitor, exclude), Blaaiz Innvoations Technology Limited, Brails Financial Inc, Belyfted Limited, Cowrie Integrated Systems Limited, Currenzo Nigeria Limited, Chime Inc (Sendwave). Seen hiring in Nigeria, register membership NOT verified: Moniepoint Group, Paystack, PayZeep (Paymi Solutions), Kredete, Cardtonic, PalmPay, Swoop. Seen in funding news, register NOT verified: Pouchers, Daya, Accrue. Full list: requires Clay research with filters: CBN register name match, Nigeria, payments hiring |
| D | African-HQ platform, marketplace, broker, exchange, payroll or wealth software business not on the CBN register, with open roles on African payments, partnerships or payouts; headcount band Not found | Seen hiring, fit and HQ NOT verified: FxPro (Payment Partnerships Manager (Africa), Nigeria and Kenya listings), Luno (Senior Manager, Payment Partnerships, Nigeria), Nilos (Head of Network Expansion and Banking Partnerships), OKX (Head of Compliance and MLRO, Nigeria), OSL (Country Manager, Africa), RemotePass (Senior Payroll Specialist, Global, Egypt and Morocco listings). PROXY (Verto customers, not Tabs): Triply, Cowrywise. Several are non-African HQ and would be C under the rule; HQ needs a Clay check |
| C | HQ outside Africa; open roles on Africa partnerships, expansion or payments | Seen in test, fit NOT verified: Taptap Send (Head of Partnerships (Africa), four listings), Coins.ph, Remitly, Kredete (UK listing). Most other hits were providers or large processors (Visa, Wise, Airwallex, WorldFirst, Payoneer, Adyen) and are excluded |
| B | African-HQ business importing, exporting or paying foreign suppliers; size Not found | PROXY only: Target Mart (Kenya, a Verto customer). Requires Clay research with filters: country NG, KE, GH, ZA, EG or CI; industry trade, logistics, manufacturing or agriculture; finance job postings |
| E | African-HQ business selling to foreign customers who needs foreign-currency receiving accounts | None verified. Requires Clay research with filters: country; export or services industries. No source for "needs a USD account" |

### Priority
| Segment | Signal density | Fit | Penetrability | Priority | Reasoning |
|---|---|---|---|---|---|
| A | High | Medium: Nomba's launch and Verto's fintech customers show demand; no Tabs customer | High: free CBN registers plus LinkedIn and Apollo data | **High** | Only segment with a verifiable account list, a dated trigger and a first register-to-jobs match (Belyfted) |
| D | Medium | Medium (PROXY: three named Verto stories, none for Tabs) | Medium: one precise jobs query works, buyers are not on a register | **Medium, test second** | API-first like Tabs; "Payment Partnerships Manager (Africa)" is a clean hook; many hits are non-African HQ |
| C | Medium | Low to medium | Medium: hits skew to providers | **Medium, low confidence** | Reachable but needs heavy exclusion |
| B | Low | Low to medium | Low: no source for "is an importer" | **Low for now** | No observable definition |
| E | Low | Low to medium | Low: no observable definition | **Low for now** | Pain is reported, accounts cannot be found |

**Decided 2026-11-13 by the user: A is the first segment.** D stays the controlled second test.

---

## Matrix 2: Signals

Four tests, each 0 to 2 (0 weak, 1 partial, 2 strong), total out of 8. **R** = clear buying reason, **V** = enough volume, **D** = data you can get, **S** = natural story. Prices were checked with `treg catalog get` before each paid call. Clay and n8n are not confirmed connected, so Clay actions below are the intended build; today's tests ran through treg.

### Universal signals (same build, keyword and filter swaps)
| # | Signal | Mother intent | Data source and exact query | Tool | Segments | R | V | D | S | Total | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|
| U1 | Hiring payments partnerships or expansion roles for Africa at a platform, broker or exchange (D1) | Hiring specific roles | LinkedIn public jobs: query `Payment Partnerships Manager Africa`, locations Nigeria and Kenya, posted within a month. Seen: FxPro x2 (2026-11-11 and 2026-11-04), Luno (2026-11-02), Nilos (2026-11-04), OKX, OSL | treg `crawl4ai.linkedin.search.jobs` ($0.00045 per call); Clay "Discover Jobs" intended | D, C | 2 | 1 | 2 | 2 | 7 | VERIFIED (PARTIAL): precise titles, small volume, HQ must be checked |
| U2 | Hiring cross-border payments, payouts, FX or treasury roles at a Nigerian operator (A2 and A3 merged) | Hiring specific roles | LinkedIn public jobs: queries `cross-border payments`, `payouts`, `settlement`, `treasury`, location Nigeria (also Kenya, Ghana), posted within a month; then join company name to the CBN registers. Keyword `payments engineer` is too loose (generic engineers) | treg `crawl4ai.linkedin.search.jobs`; Clay intended | A | 1 | 2 | 2 | 2 | 7 | VERIFIED (PARTIAL): about 1 payments-specific title in 25 for "payments engineer"; "cross-border payments" gives more (see Evidence) |
| U3 | Africa roles at a non-African company (C1) | Hiring specific roles (offshore) | LinkedIn public jobs: query `cross-border payments partnerships Africa` or `payments Africa expansion`, location United Kingdom or United States. Seen: Taptap Send x4 (2026-10-27 and 2026-10-28), Coins.ph, Remitly, Kredete | treg `crawl4ai.linkedin.search.jobs`; Clay intended | C | 2 | 1 | 2 | 2 | 7 | VERIFIED (PARTIAL): most of 25 hits are providers and large processors; needs the exclusion list |
| U4 | New head of payments, treasury or finance, under 90 days (A4) | New leadership | Apollo finds people but returns no start date; tenure needs a profile lookup | treg `apollo.people.search` (free, tested earlier); `brightdata.linkedin.user.profile` ($0.0015, not tested) | A, D | 2 | 1 | 1 | 2 | 6 | UNVERIFIED: tenure not obtainable from search alone |
| U5 | Funding round at a Nigerian cross-border fintech (A6) | Companies fundraising | Press: Pouchers $500,000 pre-seed (August 2026), Daya $2.4M pre-seed, Accrue $1.58M seed, Raenest $11M Series A (February 2025) | WebSearch (free); Crunchbase via Clay not confirmed | A | 1 | 1 | 1 | 1 | 4 | UNVERIFIED (PARTIAL): funding does exist and is reported, coverage unknown, sources are search summaries |
| U6 | Headcount growth over 20 to 25% | Headcount growth | Needs monthly Apollo or LinkedIn snapshots; none taken | none | all | 1 | 1 | 0 | 1 | 3 | PARKED |

### Niche-specific signals (new Clay build each)
| # | Signal | Mother intent | Data source | Tool | Segments | R | V | D | S | Total | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|
| N1 | Operator is on a CBN register (A1) | Account list (not a timing signal on its own) | PSP register https://www.cbn.gov.ng/PaymentsSystem/PSPs.html (279) and IMTO register https://www.cbn.gov.ng/PaymentsSystem/InternationalMoneyTransferOperators.html (108); HTML tables, names only, no dates. Re-read 2026-11-13 | WebFetch (free); Clay HTTP intended; then `crawl4ai.companies.enrich` ($0.00115 per call, by domain) or `treg.linkedin.company.profile` (about $0.001 per call) for domain and size | A | 1 | 2 | 2 | 1 | 6 | VERIFIED (COMPOUND): list is real and free; pair with U2 or N2 for timing |
| N2 | Register entity in scope of the CBN payments circular of 2026-06-15: market-structure compliance by 2026-12-31 (about 7 weeks out) and data localisation by 2027-01-01 | Regulatory changes | Scope per BusinessDay (2026-06-15): deposit money banks, microfinance banks, mobile money operators, switching companies, payment terminal service providers, payment solution service providers, super agents, other licensed payment operators. Quoted: "payments transaction data generated within Nigeria are stored and managed in Nigeria". IMTOs are NOT in that list. Reference PSS/DIR/PUB/CIR/001/004 from a regulatory database listing. Circular text not read (HTTP 429, and PwC PDF 403) | Register category from N1 as the filter | A | 1 | 2 | 2 | 1 | 6 | VERIFIED (COMPOUND): dates and scope from news; link to a Tabs need is INFERRED, and Tabs' own data-localisation status is Not found |
| N3 | IMTO subject to the naira settlement directive (circular dated 2026-03-24, effective 2026-05-01) | Regulatory changes | IMTO register (108) plus nairametrics and ThisDay coverage; circular text not read. Already in force, so it is a "now operating under it" signal, not a countdown | N1 list | A | 1 | 1 | 2 | 1 | 5 | VERIFIED (COMPOUND): weaker timing than N2 |

### Market-wide hooks and message research (not account lists)
| # | Signal | Why it is not a list source | Status |
|---|---|---|---|
| A7 | Competitor ships a cross-border rail: Nomba Global Payout API 2026-03-18, Kora stablecoin rail 2026-10-06, Verto USD accounts April 2026, Nomba hiring a Product Manager, Cross-border Payments (posted 2026-11-10) [competitors] | Timing context for A and D messaging; the hirer is a competitor | UNVERIFIED as a trigger |
| X1 | Public complaints about an incumbent's onboarding or support: 4 of the 10 newest Verto Trustpilot reviews are 1 star, about onboarding delays and silence [customers] | Reviewers are individuals; do not build a list from reviewer names; use as message research only | UNVERIFIED |
| L1 | Lookalike of confirmed customers | Needs Tabs customers; the six homepage logos are unconfirmed [customers]. PROXY lookalikes of Verto's customers are possible but untested | UNVERIFIED: unlocks if any "Trusted by" logo is confirmed |

### Considered and killed or parked
| Signal | Why |
|---|---|
| B2: importer or exporter facing FX Manual 4th edition rules (advance import payments 15% to 30%, effective 2026-06-01) | No exact source names who is an importer; fails the zero-ambiguity test [market] |
| E1: African firm that cannot receive foreign-currency payments | Press only (US bank closures, Wise limits); no data source |
| Nigeria Tax Acts: NGN5m penalty for awarding contracts to unregistered persons | Real and dated (in force 2026-01-01) but no list of firms paying foreign vendors; message hook only [market] |
| Technographics (BuiltWith) | Cannot see backend payments stack; compound only |
| Website visitors (RB2B) | Framework limits individual-level to US companies with 20k+ monthly visitors |
| Content or intent on LinkedIn | Tabs' LinkedIn has no posts and X has two [signals]; buyer posting behaviour Not found |
| Provider hiring (PingPong Payments, XTransfer, Duplo, Nomba) | These are competitors or adjacent providers; market intelligence only |

### Universal or niche-specific
U1, U2 and U3 are the same LinkedIn jobs build with different keywords and locations: **universal, build once, three uses**. N1, N2 and N3 share one register scrape and differ only by category filter: **niche-specific, one build, three uses**. U4 and U5 need new builds and stay unverified. So 3 universal workflows and 1 niche build cover five planned workflows.

**Join test (first sample).** Comparing the 25 IMTO names read with the six jobs pulls found one match: Belyfted Limited (IMTO register entry 7) posted a Full Stack Developer role in Lagos on 2026-10-27. One match in a 25-name sample proves the join works, not what its yield is; the full 387 names (279 plus 108) are needed. [Evidence]

---

## Evidence (all 2026-11-13)
**CBN registers (free fetches).** PSP register: 279 licensees, counts per category as listed in N1; the page shows no date. IMTO register: 108 operators, numbered 1 to 108, names only, no date; first 25 read (Acha Global Hub Limited to E27 Partners UK Limited). IMTO licences cover inbound transfers [market], so only some IMTOs are Tabs prospects. INFERRED.

**CBN payments circular.** BusinessDay, published 2026-06-15: scope list and quote as in N2; attributed to Rakiya Yusuf, director, Payments System Supervision Department; deadlines 2026-12-31 and 2027-01-01; monthly market-share returns. Source: https://businessday.ng/technology/article/cbn-ends-offshore-payment-processing-as-banks-fintechs-face-2027-data-localisation-deadline/ . The circular text itself was not read.

**LinkedIn jobs (treg `crawl4ai.linkedin.search.jobs`, six calls at $0.00045, 25 rows each, posted within a month). Reads are mine, by eye.**
| Query | Location | Read |
|---|---|---|
| payments Africa expansion | United States | Mostly large processors and card networks (Visa, Mastercard, Global Payments, Capital One); Africa-relevant: Taptap Send Head of Partnerships (Africa), Wave Mobile Money |
| payments engineer | Nigeria | Nigerian fintech and payments employers dominate (Moniepoint 2, Paystack 2, Cardtonic, PayZeep, Kredete, PalmPay, Nomba) but roles are generic engineering; one payments-specific title (Nomba, a competitor); noise from Canonical and Ericsson |
| payouts Africa platform marketplace | Remote | African payments employers (Paymob, PalmPay, PawaPay, Thunes, FxPro x2, RemotePass x2, Wave x2, MTN MoMo Ghana, PingPong Payments); two Canonical roles are noise |
| cross-border payments partnerships Africa | United Kingdom | Almost all providers and large processors (Taptap Send, Airwallex, WorldFirst, Wise, Payoneer, Adyen, Stripe); Kredete is the one Nigerian fintech |
| cross-border payments | Nigeria | Providers (PingPong Payments, XTransfer, Nomba, Taptap Send, Duplo) plus platform candidates (Luno, FxPro x2, Nilos, OKX, OSL, Caliza); Moniepoint, Paystack, PalmPay roles are not payments-specific |
| FX treasury settlement payouts | Nigeria | Mostly generic finance roles (CFO, finance managers, accountants); low precision, so U2 should not use treasury keywords alone |

**Apollo people search (treg `apollo.people.search`, free, no emails; earlier run today, not re-run).** All-industry loose title matches, not fits: head of treasury, payments, finance or CFO in Nigeria 2,708; head of compliance, CCO or MLRO in Nigeria 2,817; payments engineer, head of engineering or product in Nigeria 640; head of payments or partnerships in Kenya, Ghana, South Africa and Egypt 700. Apollo has no industry filter in this endpoint, so the CBN register is the precision filter. INFERRED.

**Funding examples (press, search summaries, not read in full).** Pouchers: https://ffnews.com/news/pouchers-secures-500000-pre-seed-funding-to-scale-global-payments-for-nigerians . Daya: https://www.intellinews.com/nigeria-s-daya-raises-2-4mn-to-expand-stablecoin-payment-network-across-africa-450796/ . Accrue: https://msmeafricaonline.com/nigerian-fintech-startup-accrue-raises-1-58-million-seed-round/ . Raenest: https://techcrunch.com/2025/02/11/qed-leads-11m-investment-in-nigerian-fintech-raenest .

**Spend.** This rebuild: $0.0027 on treg (six jobs calls; balance 0.97485 to 0.97215). The research refresh earlier spent $0.02035. Session total on treg: about $0.0231 for these two passes. Web searches and fetches were free.

---

## Build first
| Rank | Signal | Why |
|---|---|---|
| 1 | **N1 + U2** register joined to hiring | Only verifiable, free, finite account list (387 names) joined to a weekly trigger; the first sample produced a real match (Belyfted) |
| 2 | **N2** CBN circular exposure by register category | The one hard date: 2026-12-31 and 2027-01-01, under 7 weeks out. Weakness: scope from news, and Tabs' own localisation status is Not found, so the pitch cannot claim to solve it |
| 3 | **U1** Payment Partnerships (Africa) roles | Cleanest title hit in the test; opens segment D; needs an HQ check |
| 4 | **U3** Africa roles outside Africa | Cheap, same build; needs the exclusion list |

Held back: U4 until a tenure source is tested; U5 until news search is systematised; U6, B2, E1.

**Suggested first workflow.** Mother intent: hiring cross-border payments, payouts or FX roles in Nigeria. ICP filter: company name matches the CBN PSP or IMTO register, Nigeria-based, not on the provider exclusion list. Secondary enrichments: register category, headcount and domain from the company profile, persona counts from Apollo. Spec next with `/build-workflow-spec`.

---

## Matrix 3: Workflow tracker (pre-filled, validated signals only)
| W # | Status | Workflow name | Mother intent |
|---|---|---|---|
| 1 | Planned | Cross-border payments hiring at CBN-registered operators (N1 + U2) | Hiring specific roles |
| 2 | Planned | CBN circular deadline exposure by register category (N1 + N2) | Regulatory changes |
| 3 | Planned | Payment Partnerships (Africa) roles at platforms and brokers (U1) | Hiring specific roles |
| 4 | Planned | Africa roles outside Africa (U3) | Hiring specific roles (offshore) |
| 5 | Planned | IMTO naira settlement exposure (N1 + N3) | Regulatory changes |

Backlog, not in the tracker until tested: U4 (new leadership), U5 (funding), L1 (lookalike). Other tracker columns are filled as campaigns launch.

## Open questions
- Which segment first? Decided: A (2026-11-13). D is the second test.
- Is Clay connected, and is Apollo available beyond free search? That decides enrichment and U4.
- Which of the 387 register entries are competitors or consumer apps to exclude, and are consumer remittance apps in or out as buyers?
- Are any of the six "Trusted by" logos customers? That would unlock L1.
- Can someone read the CBN payments circular PDF to confirm deadlines and who is covered?
- Do we need an HQ lookup to split D from C before running U1?
- Is X1 (incumbent complaints) acceptable as message research, and is Trustpilot a permitted source?
