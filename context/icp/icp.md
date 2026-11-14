# ICP: Tabs Global

Built only from `context/docs/research/`. Tags: [company], [customers], [competitors], [market], [signals], [voice] = research file. INFERRED = my reading, not a source statement. There is no customer list or interview data, so this is a hypothesis to test, not a validated ICP.

## Read this first
The first draft listed who Tabs may legally serve and restated Tabs' product features. That is not an ICP. The research supports three segments to test, each with the layers below. Segments are ranked by how much evidence exists, which is not much.

## Segments to test
| # | Segment | Why it is a candidate | Evidence strength |
|---|---|---|---|
| A | Nigerian payment firms and fintechs paying out abroad | Nomba's Global Payout API targets "Nigerian payment firms and businesses" and quotes the problem: "Operators collect naira, then go source foreign currency, all while their customers are waiting." Tabs lists "FINANCIAL SOFTWARE" as a use case. [competitors], [customers] | Medium: a competitor proves demand; no Tabs customer confirmed |
| B | African businesses paying or receiving across borders for trade | Tabs' labels "GLOBAL TRADE" and "SUPPLIER PAYMENTS" and "African businesses trading globally"; FX Manual 2026 changes import payment rules from 1 June 2026. [customers], [voice], [market] | Low to medium: Tabs' own copy plus regulation; no buyer data |
| C | Non-African businesses paying into Africa | LinkedIn: "We enable global businesses move money seamlessly across the continent." Verto targets US businesses paying into Africa. [company], [competitors] | Low: positioning line and a competitor's focus only |

Unproven for all three: size, stage and industry of a real buyer. [customers]

## Five layers (what to check per account)

### 1. Firmographic
| Attribute | Value | Source |
|---|---|---|
| Customer type | Businesses only | [company] Terms |
| Geography | Operates in or pays into Nigeria first (docs); Kenya, Ghana, South Africa, Egypt, Côte d'Ivoire per homepage, unconfirmed live | [company] |
| Size, stage, headcount, revenue | Not found. First task: get this from the first conversations | [customers] |
| Industry | Segment A: payments and fintech. Segment B: traders and importers. Segment C: not specified | see segments |

### 2. Technographic (qualifying conditions, not evidence of demand)
These come from what Tabs offers, so they say what a buyer needs to be able to do, not that buyers want it.
- Can integrate a REST API and use a sandbox, idempotency keys and signed webhooks, or has someone who can. [company]
- Pays out on local rails and holds USD, EUR or GBP balances, or needs to. [company]
- Today's provider or stack: Not found, so ask on every call.

### 3. Intent signals
Market-wide timing (applies to many accounts, not account-level proof):
- IMTO naira settlement directive, effective 1 May 2026. FX Manual 2026, effective 1 June 2026. Market share returns by 31 Dec 2026. Data localisation from 1 Jan 2027. [market]
- Competitor launch: Nomba Global Payout API, 18 Mar 2026. [competitors]

Account-level signals: Not found. No target list exists and no hiring, funding or new-finance-leader searches were run. [signals]

### 4. Persona
Champion (engineering or product), economic buyer (finance or operations), influencer (compliance or treasury). All INFERRED, titles Not found. See [personas.md](personas.md).

### 5. Engagement readiness
- Tabs' entry points: "Get a demo", "Read the docs", sandbox "Every rail, no contract". [company], [voice]
- INFERRED: "Start with one market. Keep the same integration." points to a single-market pilot. [voice]
- No public pricing, so first contact is a demo. [company]
- Budget, timeline, buying process: Not found.

## Not a fit
Hard exclusions (rules Tabs publishes):
- Individuals, freelancers, consumers. [company] Terms
- Shell companies, sanctioned persons, anyone failing KYB. [company] compliance page
- Anyone who needs a country or product Tabs has not confirmed ("Not all products, currencies or countries ... may be available"). [company] Terms

Poor fit, INFERRED from gaps in what Tabs lists:
- Teams that need cards or overdrafts; Flutterwave and Nomba list them, Tabs does not. [competitors], [company]
- Businesses that need public pricing or a named licence before a call. Tabs publishes neither. [company]

## What would make this a real ICP (next research)
1. Confirm which of the six "Trusted by" logos are customers, and what they use Tabs for. [customers]
2. Interview or find buyers in segment A to get titles, KPIs and the current provider.
3. Build a target list for one segment, then collect hiring and funding signals per account. [signals]
4. Confirm which countries are live.

## Open questions
- Who uses Tabs today?
- Which segment should be tested first?
- Real size and stage of the buyer.
