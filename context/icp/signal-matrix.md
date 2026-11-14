# Signal Matrix: Tabs Global (draft, rebuilt 2026-11-13)

Rebuilt from scratch from `context/icp/icp.md`, `context/icp/personas.md`, `context/positioning/`, `context/docs/research/` and the playbooks `signal-matrix-framework.md` and `workflow-anatomy.md`. This is a work-in-progress for a strategy session, not a final deliverable. Tags: [company], [customers], [competitors], [market], [signals] = research file. INFERRED = my reading, not supported by the research. "Seen in test" = from a tool call or page fetch made today, listed under Evidence.

**What Tabs sells.** Tabs Connect: an API for cross-border payouts, collections, USD, EUR and GBP accounts and FX for businesses moving money into and out of Africa. Single product. No customers confirmed. [company], [customers]
**Competitors that matter here.** Nomba, Kora, Raenest, Grey, Flutterwave, Verto. [competitors]
**Data reality.** Africa has no Crunchbase-grade coverage, but two things work: LinkedIn jobs and Apollo people search return Nigerian data, and the CBN publishes licensed-operator registers as free HTML tables (see Evidence).
**Tools connected.** treg only (LinkedIn jobs and company, X, Apollo people search). Clay is named in the framework but not confirmed connected, so Clay steps are marked as such.

---

## Matrix 1: Segments x Personas

Rows are the segments from icp.md. Columns are the three INFERRED personas from personas.md. Each cell is the angle, written as a situation, not a diagnosis. Pillars refer to messaging.md.

| Segment | Champion (engineering or product) | Economic buyer (finance or ops) | Influencer (compliance or treasury) |
|---|---|---|---|
| **A. Nigerian payment firms and fintechs paying out abroad** | "As you add corridors, one endpoint per market means no new integration each time." (Pillar 1) | "Collect naira, pay out in USD, EUR or GBP, and lock a quote for 60 seconds before you commit." (Pillars 2, 3) | "Screening and recipient name checks run before money moves, ahead of the 2026 CBN dates." (Pillar 4, dates in [market]) |
| **B. African businesses paying or receiving across borders for trade** | INFERRED: usually no engineer in this role; skip or merge with the economic buyer. | "Supplier payments from one balance, with a locked FX quote." (Pillars 2, 3) Link to the 2026 FX Manual is INFERRED because its import documentation rules were not found. | Not found. Do not claim FX Manual documentation support. Use Pillar 4 basics only. |
| **C. Non-African businesses paying into Africa** | "Start with one market. Keep the same integration." (Pillar 1) | "Hold USD, EUR or GBP and pay out on local rails from one balance." (Pillar 2) | "KYB and screening on the recipient side." (Pillar 4) |

### Target definitions (observable, filterable)
| Segment | Definition | Company examples |
|---|---|---|
| A | Entities on the CBN licensed registers (Payment Service Providers: mobile money, switching and processing, payment solution services; International Money Transfer Operators) that are Nigeria-based and pay out or collect across borders. The register is the filter. | Seen in test, fit NOT verified: AFEX, Cellulant, Smartcash PSB, B Transfer (Apollo results); Moniepoint, Paystack, PayZeep, Kredete, Cardtonic (hiring). On the IMTO register: AFRIEX INC, BLAAIZ INNVOATIONS TECHNOLOGY LIMITED, BRAILS FINANCIAL INC. Several are competitors or consumer-remittance apps, so exclusions are needed. Full list: Requires Clay research with filters: CBN register name match, Nigeria, payments hiring |
| B | African-HQ businesses importing, exporting or paying foreign suppliers [customers: "GLOBAL TRADE", "SUPPLIER PAYMENTS"]. Size not found. | Requires Clay research with filters: country NG, KE, GH, ZA, EG or CI; industry trade, logistics, manufacturing or agriculture; finance job postings. No example verified |
| C | Non-African-HQ businesses with open roles on Africa partnerships, expansion or payments [company: "global businesses"] | Seen in test, fit NOT verified, mostly providers: Taptap Send, WorldFirst, EBANX, Thunes. Requires Clay research with filters: HQ outside Africa; "Africa" plus payments or partnerships titles |

### Priority
| Segment | Signal density | Fit | Penetrability | Priority | Reasoning |
|---|---|---|---|---|---|
| A | High | Medium: a competitor proves demand, no Tabs customer [competitors] | High: free CBN registers plus LinkedIn and Apollo data | **High** | Only segment with a verifiable account list and dated timing |
| C | Medium | Low to medium [competitors: Verto's focus] | Medium | **Medium** | Reachable, but hits skew to payment providers |
| B | Low | Low to medium [customers] | Low: no source for "is an importer" | **Low for now** | No observable definition yet |

---

## Matrix 2: Buying signals

Four tests, each 0 to 2 (0 weak, 1 partial, 2 strong), total out of 8. **R** = clear buying reason, **V** = enough volume, **D** = data you can get, **S** = natural story. Status per the framework. Prices were checked with `treg catalog get` before each paid call.

### Segment A: Nigerian payment firms and fintechs
| # | Signal | Mother intent | Data source | Tool | R | V | D | S | Total | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| A1 | Operator is on a CBN register and faces a dated rule (IMTO naira settlement from 1 May 2026; payments framework: market share returns by 31 Dec 2026, data localisation from 1 Jan 2027) | Regulatory changes | CBN PSP register (https://www.cbn.gov.ng/PaymentsSystem/PSPs.html, about 279 entries across 6 categories) and IMTO register (https://www.cbn.gov.ng/PaymentsSystem/InternationalMoneyTransferOperators.html, 108 IMTOs). Rules: [market]; the CBN payments circular PDF exists on cbn.gov.ng but could not be read, so deadlines still rest on a law-firm summary | WebFetch (free) now; Clay HTTP per framework (not confirmed). Names only, so add `crawl4ai.companies.enrich` ($0.00115 per call, by domain) or `treg.linkedin.company.profile` to get domain, size and site | 1 | 2 | 2 | 1 | 6 | VERIFIED (COMPOUND): registers are real and free; link to a Tabs need is INFERRED |
| A2 | Hiring payments, backend or treasury roles in Nigeria | Hiring specific roles | LinkedIn public job listings | treg `crawl4ai.linkedin.search.jobs` ($0.00045 per call) | 1 | 2 | 2 | 2 | 7 | VERIFIED: sample pulled |
| A3 | Hiring cross-border payments, partnerships or FX roles | Hiring specific roles | LinkedIn public job listings | treg `crawl4ai.linkedin.search.jobs`; alt `treg.companies.jobs.search` (variable) | 2 | 1 | 2 | 2 | 7 | VERIFIED (PARTIAL): many hits are providers or competitors |
| A4 | New head of payments, treasury or finance (under 90 days) | New leadership | Apollo finds the people but returns no start date, only a refresh date. Tenure needs a profile lookup | treg `apollo.people.search` (free, tested); `brightdata.linkedin.user.profile` ($0.0015, experience dates, not tested) | 2 | 1 | 1 | 2 | 6 | UNVERIFIED: tenure not obtainable from search alone |
| A5 | Announces a new African market or licence | New product launches | Press (seen in test: Fincra Ghana licence 6 May 2026, MoMo PSB Kenya expansion Jan 2026, Onafriq and PAPSS naira-to-Ghana pilot Feb 2026) | WebSearch; not systematised | 2 | 1 | 1 | 2 | 6 | UNVERIFIED (search summaries only; most names are providers, not buyers) |
| A6 | Funding round for a Nigerian fintech | Companies fundraising | Press (seen in test: Nairagram $6m Feb 2026; Pouchers $500K pre-seed) | WebSearch; Crunchbase via Clay not confirmed | 1 | 1 | 1 | 1 | 4 | UNVERIFIED: framework allows it only in VC markets; some African fintech funding exists, coverage unknown |

### Segment B: African trade businesses
| # | Signal | Mother intent | Data source | Tool | R | V | D | S | Total | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| B1 | Hiring treasury, trade finance or finance manager roles | Hiring specific roles | LinkedIn public job listings | treg `crawl4ai.linkedin.search.jobs` | 1 | 2 | 2 | 1 | 6 | VERIFIED (PARTIAL): sample mostly NGOs and consultancies |
| B2 | Business is an importer or exporter facing FX Manual rules | Regulatory changes | No exact source named | None | 2 | 0 | 0 | 1 | 3 | KILLED: fails the zero-ambiguity test |

### Segment C: Non-African businesses paying into Africa
| # | Signal | Mother intent | Data source | Tool | R | V | D | S | Total | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| C1 | Hiring Africa partnerships, expansion or payments roles outside Africa | Hiring specific roles (offshore) | LinkedIn public job listings, location set to the HQ country | treg `crawl4ai.linkedin.search.jobs` | 2 | 2 | 2 | 2 | 8 | VERIFIED (PARTIAL): many hits are payment providers |
| C2 | Public announcement of an Africa launch | New product launches | Press and company news | WebSearch or WebFetch; not tested | 1 | 1 | 1 | 2 | 5 | UNVERIFIED |

### Considered and killed or parked
| Signal | Why |
|---|---|
| Technographics (BuiltWith) | Cannot see backend payments stack; compound only. |
| Website visitors (RB2B) | Framework limits individual-level to US companies with 20k+ monthly visitors. |
| Content or intent on LinkedIn | Tabs' LinkedIn returned no posts and X has two [signals]; buyer posting behaviour Not found. |
| Headcount growth | Needs monthly Apollo or LinkedIn snapshots; nothing tested, so parked. |

### Universal or niche-specific
A2, A3, B1 and C1 are the same LinkedIn jobs build with different keywords and locations, so they are **universal** (build once, four uses). A1 is **niche-specific** (CBN registers). A4 to A6 need new builds.

---

## Evidence (all 2026-11-13)
**CBN registers (free fetches).**
- PSP register: about 279 entries in six categories: Card/Payment Schemes (8), Mobile Money Operators (17), Switching and Processing (19), Payment Solution Services (about 232), Payments Service Holding (1), Terminal Service Aggregator (2). HTML tables, no licence dates. Counts are from the fetch tool's row count.
- IMTO register: 108 operators, name and address only, no dates. Nairametrics reported 62 in Feb 2024, with only five names in text (Flutterwave, Interswitch, Paga, Xpress Payment Solutions, Paycom), so the register has grown.
- IMTO licences cover inbound transfers [market], so only some IMTOs are Tabs prospects. INFERRED.

**Apollo people search (treg `apollo.people.search`, free, 0 credits, returns no emails).** Counts are all-industry loose title matches, not fits:
| Titles | Location | Total entries |
|---|---|---|
| Head of treasury, head of payments, head of finance, CFO | Nigeria | 2,708 |
| Head of compliance, CCO, MLRO | Nigeria | 2,817 |
| Payments engineer, head of engineering, head of product | Nigeria | 640 |
| Head of payments, head of partnerships | Kenya, Ghana, South Africa, Egypt | 700 |

Sample orgs include banks, a PSB and insurers (Access Bank, PremiumTrust Bank, Smartcash PSB, NEM Insurance, Unity Bank), plus AFEX, Cellulant, B Transfer and Equity Bank. Apollo gives no industry filter in this endpoint, so the CBN register is the precision filter. INFERRED.

**LinkedIn jobs (treg `crawl4ai.linkedin.search.jobs`, four calls at $0.00045, pulled earlier today).**
| Query | Location | Rows | Read |
|---|---|---|---|
| payments engineer | Nigeria | 25 | Moniepoint Group, Paystack, PayZeep, Kredete, Cardtonic; noise (Canonical, Ericsson) |
| treasury manager | Nigeria | 25 | Mostly NGOs and consultancies |
| cross-border payments | Kenya | 18 | Mostly providers (Thunes, Verto, Wave Mobile Money) |
| payments Africa expansion | United Kingdom | 25 | Mostly payment companies |

**Spend.** This rebuild: $0 new (Apollo search and web fetches are free). Session treg total is about $0.0048; balance $0.9952.

---

## Build first
| Rank | Signal | Why |
|---|---|---|
| 1 | **A1** CBN register as the account list | It is the only verifiable, free, finite list (about 279 PSP entries plus 108 IMTOs) and it fixes the noise in the jobs data. It also carries the one hard date: market share returns by 31 December 2026 and data localisation on 1 January 2027, about seven weeks out. Weakness: names only, and Tabs' link to these rules is INFERRED. |
| 2 | **A2** Hiring payments roles | Verified, cheapest, repeatable weekly. Run it as the trigger and match the hiring companies against the A1 list to drop noise. |
| 3 | **A3** Hiring cross-border or partnerships roles | Closest to a direct buying reason. Needs a competitor exclusion list. |
| 4 | **C1** Africa roles outside Africa | Highest score (8), the same build as A2 and A3, and opens segment C. |

Held back: A4 until a tenure source is tested; A5 and A6 until news search is systematised; B1 until precision improves.

**Suggested first workflow.** Mother intent A2 or A3 (hiring); ICP filter: company name matches the CBN PSP or IMTO register and is Nigeria-based; secondary enrichments: register category, headcount and domain from company profile, and persona count from Apollo. Spec it next with `/build-workflow-spec`.

---

## Matrix 3: Workflow tracker (pre-filled)
| W # | Status | Workflow name | Mother intent |
|---|---|---|---|
| 1 | Planned | Hiring payments roles, CBN-registered Nigerian operators | Hiring specific roles |
| 2 | Planned | CBN deadline exposure | Regulatory changes |
| 3 | Planned | Hiring cross-border or partnerships roles | Hiring specific roles |
| 4 | Planned | Africa roles outside Africa | Hiring specific roles (offshore) |

Other tracker columns are filled as campaigns launch.

## Open questions
- Which segment first? This draft assumes A.
- Is Clay connected, and is Apollo available beyond free search? That decides enrichment and A4.
- Which register entries are competitors or consumer remittance apps to exclude?
- Are the six "Trusted by" logos customers? That would unlock a lookalike signal. [customers]
- Can someone read the CBN payments circular PDF to confirm deadlines and who is covered?
