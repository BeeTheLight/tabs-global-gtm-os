# Value proposition by persona

Reconciled 2026-11-13 with the refreshed `context/docs/research/`. Personas are INFERRED hypotheses (see [personas.md](../icp/personas.md)). Tags: [company], [customers], [competitors], [market], [voice]. "Proof" lists what exists today; where it is thin, that is stated. Wording below was re-checked on the live Tabs homepage on 2026-11-13: "One ledger where every local currency settles into your preferred currency." and "KYB, screening and transaction monitoring run inside the payment flow, with audit trails included." are both confirmed (the audit-trails line is in the homepage FAQ, not on the compliance page). Not re-confirmed, so treat as unverified: "board-approved AML policy" (absent from the compliance page as fetched on 2026-11-13).

| | Champion (engineering or product) | Economic buyer (finance or ops) | Influencer (compliance or treasury) |
|---|---|---|---|
| Job to be done | Add payouts and collections across African markets without building each integration | Pay and get paid across borders quickly and predictably | Move money within the rules, with screening and an audit trail |
| Pain | Separate integration per market; duplicate payouts [voice] | High cost and slow settlement to Africa (about 7.9% to send $200, per press) [market] | New CBN deadlines and counterparty checks [market] |
| Gain | "One endpoint per market you were going to integrate separately." and "Start with one market. Keep the same integration." [voice] | One ledger where "every local currency settles into your preferred currency"; USD, EUR, GBP accounts with FX built in [company] | KYB, screening and transaction monitoring "run inside the payment flow, with audit trails included"; recipient names verified before money moves [voice] |
| Proof | REST API with idempotency keys, HMAC-signed webhooks, sandbox, 60-second FX quotes, documented endpoints [company]. No named customer. | Stated settlement "<5 min", local rails "Instant · 24/7" [company] (self-reported). Pricing proof: none published. | Compliance page: funds held with licensed partners, separate from operating funds; Nigeria Data Protection Commission trust mark [company]. "Board-approved AML policy" could not be re-confirmed and is dropped. No licence numbers. |
| Proof gaps | No customer or case study [customers] | "$100m+" processed unverified; fee is a demo value [company] | Partner banks unnamed; data localisation status Not found [company], [market] |

## Notes
- Every proof item above is Tabs' own claim. No third-party validation was found. [customers]
- Do not use the "$100m+" figure or the 0.01% fee in copy until confirmed. [company]
- Open question: which of the six "Trusted by" logos can be named as customers. [customers]
- Incumbent benchmark (PROXY): Verto customer stories state the pains as bank FX cost, daily caps, slow documentation and multi-day settlement; none of those has been tested as a Tabs buyer pain. [customers]
