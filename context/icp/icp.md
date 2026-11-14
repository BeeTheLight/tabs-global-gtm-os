# ICP: Tabs Global

Reconciled 2026-11-13 with the refreshed research in `context/docs/research/`. Tags: [company], [customers], [competitors], [market], [signals], [voice] = research file. INFERRED = my reading, not a source statement. PROXY = evidence from Verto or WeWire, the two incumbents we use because Tabs has none of its own. A PROXY fact shows what buyers of a Verto-like company look like; it is not a Tabs customer fact. There is still no Tabs customer list or interview data, so this is a hypothesis to test, not a validated ICP.

## Read this first
Tabs Global has no named customers, case studies or pricing [customers], [company]. The refresh found that the incumbents publish a lot: Verto names customers and case studies, and both publish who they serve. That lets us sharpen the segments below, but only as proxy evidence. What changed since the last version:
- Two segments added to test (D platforms, E African firms needing foreign-currency accounts), both from proxy evidence.
- Evidence strength re-rated per segment, with proxy and Tabs-own evidence kept apart.
- Competitor exclusion list expanded (Verto, WeWire, Kora, Fincra, Yellow Card, Thunes added).
- Dated triggers updated with circular dates and the tax acts [market].

## Segments to test
| # | Segment | Why it is a candidate | Evidence strength |
|---|---|---|---|
| A | Nigerian payment firms and fintechs paying out abroad | Tabs lists "Financial software" as a use case [voice]. Nomba's Global Payout API (2026-03-18) targets "cross-border payment operators, remittance platforms, and fintechs" [competitors]. PROXY: Verto Atlas is sold to "fintechs (PSPs, banks)" and Verto names d.local, Lemfi, Paystack, MTN [customers] | Medium: competitor launch plus proxy customers; no Tabs customer |
| B | African businesses paying or receiving across borders for trade | Tabs labels "Global trade" and "Supplier payments" [voice]. PROXY: Target Mart, a Kenyan beauty and FMCG distributor, left bank FX for Verto after high forex rates, hidden fees, daily caps and slow documentation [customers]. WeWire names import/export and "100+ International Manufacturers & Suppliers" [customers]. Dated rule: FX Manual 4th edition from 2026-06-01 [market] | Low to medium: one proxy story plus regulation; no buyer data for Tabs |
| C | Non-African businesses paying into Africa | LinkedIn About: "We enable global businesses move money seamlessly across the continent." [company]. PROXY: Verto launched USD business accounts for US to Africa flows (April 2026) [competitors]; WeWire offers USD, GBP and EUR accounts and registers businesses in the US, UK, Canada and UAE [company] | Low to medium: positioning line plus incumbent moves |
| D (new) | Platforms, marketplaces and vertical software that need to pay or collect in Africa through an API | PROXY: Verto Atlas for Platforms (marketplaces, SaaS, expense management, brokers); Triply (travel platform) integrated Atlas for virtual accounts, conversion and payouts; Cowrywise (Lagos wealth platform) uses Verto's API for FX and broker payouts [customers], [competitors] | Medium (proxy): three named stories; none for Tabs |
| E (new) | African businesses that need USD, EUR or GBP accounts to get paid by foreign customers | Tabs FAQ: "African businesses can hold USD, EUR and GBP accounts with FX built in." [company]. Reports of US banks closing African startup accounts and Wise suspending dollar transfers from Nigeria [market]; PROXY: Verto USD accounts (April 2026) [competitors] | Low to medium: pain reported in press only; many of the sources sell competing products |

Unproven for all five: size, stage and industry of a real Tabs buyer. [customers]

## Five layers (what to check per account)

### 1. Firmographic
| Attribute | Value | Source |
|---|---|---|
| Customer type | Businesses only | [company] compliance page and Terms |
| Geography | Operates in or pays into Nigeria first (docs name only Nigeria); Kenya, Ghana, South Africa, Egypt, Côte d'Ivoire named on the homepage, unconfirmed live | [company] |
| Size, stage, headcount, revenue | Not found for Tabs. PROXY range: Verto's named customers run from startups to MTN-size groups; Target Mart, Triply and Cowrywise sizes are not stated. First task: get this from the first conversations | [customers] |
| Industry | A and D: payments, fintech, software. B: importers, distributors. C: not specified. E: not specified | see segments |

### 2. Technographic (qualifying conditions, not evidence of demand)
These come from what Tabs offers, so they say what a buyer needs to be able to do, not that buyers want it.
- Can integrate a REST API and use a sandbox, idempotency keys and signed webhooks, or has someone who can. [company]
- Pays out on local rails and holds foreign-currency balances, or needs to. [company]
- Today's provider or stack: Not found. Candidate incumbents to ask about on every call: Verto, WeWire, Nomba, Kora, Fincra, a bank. [competitors]

### 3. Intent signals
Market-wide timing (applies to many accounts, not account-level proof). Dates and sources in [market]:
- Nigeria Tax Acts in force 2026-01-01; NGN5m penalty for awarding contracts to unregistered persons.
- IMTO naira settlement circular dated 2026-03-24, effective 2026-05-01.
- FX Manual 4th edition, effective 2026-06-01 (advance import payments from 15% to 30%, reported).
- CBN payments framework circular of 2026-06-15: market-share compliance by 2026-12-31, data localisation by 2027-01-01.
- Competitor launches: Nomba Global Payout API 2026-03-18; Kora stablecoin rail 2026-10-06; Verto USD accounts April 2026. [competitors]
Account-level signals: still no reliable list. Hiring signals were tested and are noisy (see signal-matrix.md). [signals]

### 4. Persona
Champion (engineering or product), economic buyer (finance or operations), influencer (compliance or treasury). Titles are still INFERRED for Tabs; PROXY titles seen at Verto customers are CTO, CEO and Commercial Director. See [personas.md](personas.md).

### 5. Engagement readiness
- Tabs' entry points: "Get a demo", "Read the docs", "Talk to us", sandbox "Every rail, no contract". [company], [voice]
- INFERRED: "Start with one market. Keep the same integration." points to a single-market pilot. [voice]
- No public pricing from Tabs, so first contact is a demo. Both incumbents publish prices or plans (WeWire a full fee table, Verto plans), so buyers who compare may expect a number. [company], [competitors]
- Onboarding speed may matter: recent Verto Trustpilot reviews complain about onboarding delays and silence. [customers], [signals]
- Budget, timeline, buying process: Not found.

## Not a fit
Hard exclusions (rules Tabs publishes):
- Individuals, freelancers, consumers. [company]
- Shell companies, shell banks, sanctioned persons, anyone failing KYB. [company]
- Anyone who needs a country or product Tabs has not confirmed ("Not all products, currencies or countries described on the Website may be available at any given time"). [company] Terms

Competitors and providers (exclude as targets; ask about them as the incumbent): Verto, WeWire, Nomba, Kora, Fincra, Flutterwave, Yellow Card, Thunes, Raenest, Grey, Afriex, Cleva, WorldFirst. [competitors]

Poor fit, INFERRED from gaps in what Tabs lists:
- Teams that need cards or overdrafts as the first product; Flutterwave and Nomba list them, and Verto lists corporate cards, while Tabs lists none. [competitors], [company]
- Businesses that need a named licence, named partner bank or published pricing before a call. Tabs publishes none; Verto names its FCA firm reference and WeWire names FINTRAC and Mauritius licences. [company], [competitors]
- Treasury teams needing OTC desks or trade finance as the first product: WeWire and Verto offer them, Tabs lists none. [competitors]

## What would make this a real ICP (next research)
1. Confirm which of the six "Trusted by" logos are customers and what they use Tabs for. [customers]
2. Interview or find buyers in A and D to get titles, KPIs and the current provider.
3. Build a target list for one segment, then collect account-level signals. [signals]
4. Confirm which countries are live and whether Tabs holds, or relies on partners for, the licences its features need. [company], [market]
5. Test whether proxy case-study pains (bank FX cost, daily caps, slow documentation, multi-day settlement) match what Tabs prospects say.

## Open questions
- Who uses Tabs today?
- Which segment first? DECIDED 2026-11-13 by the user: **A first**. D is the second test; D rests on proxy evidence.
- Real size and stage of the buyer.
