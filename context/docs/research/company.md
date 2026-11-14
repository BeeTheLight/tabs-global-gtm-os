# Tabs Global: company facts

Raw research, not conclusions. Refreshed 2026-11-13. Every fact has a source URL and was checked on 2026-11-13 unless a different date is shown. "Not found" means searched and absent. INFERRED means my reading, not a source statement.

**How to read this file.** Tabs Global is new and publishes little. Where Tabs has no public answer, this file shows what the two named incumbents publish, labelled PROXY (Verto) or PROXY (WeWire). A proxy fact is NOT a Tabs fact and must not be used as one in copy.

**Capture caveat.** Page text was read through a summarising fetch tool, so quotes are short and should be re-checked against the live page before use in copy.

**Name collision warning.** "Tabs" (tabs.inc, New York, AI accounts receivable, $7M seed from Lightspeed, April 2024) is a different company. Its funding and founders do not apply to Tabs Global. Source: https://www.businesswire.com/news/home/20240411085880/en/Tabs-Secures-%247M-in-Seed-Funding-Led-By-Lightspeed-to-Advance-its-AI-powered-B2B-Accounts-Receivable-Platform
**Second collision:** the X account @TabsNetwork belongs to Tabs Global (its website field is tabsglobal.co), so "Tabs Network" in search results is the same company.

## What Tabs sells

- Homepage headline: "Borderless money movement for Africa". Source: https://tabsglobal.co/
- Homepage sub-line: "Global banking infrastructure for African businesses." Source: https://tabsglobal.co/
- FAQ "What is Tabs?": "Tabs is a cross-border payments platform that moves money into and out of Africa." Covers payouts, local collections and global business accounts through one API. Source: https://tabsglobal.co/
- LinkedIn About: "Tabs is the payment infrastructure for Africa. We enable global businesses move money seamlessly across the continent." Source: https://www.linkedin.com/company/tabsglobal (via treg crawl4ai.linkedin.company.profile)
- API product name Tabs Connect appears in the docs. Source: https://docs.tabsglobal.co
- Customer type: businesses only. Source: https://tabsglobal.co/compliance
- PROXY (Verto): "Cross border payment solutions for global businesses", for "startups, mid-size companies, and enterprises". Source: https://verto.co/
- PROXY (WeWire): "Virtual Business Accounts & Cross-Border Payment APIs for Global Businesses". Source: https://www.wewire.com/

## Modules and features

**Tabs** (homepage menu): Payouts, Collections, Global accounts, Coverage. Developer menu: Documentation, API reference, Sandbox, Status. Use-case tags: Global trade, Supplier payments, Financial software. Source: https://tabsglobal.co/

From the docs index (https://docs.tabsglobal.co/llms.txt):
- Wallets: list wallets, get a wallet balance, get a virtual account, generate a crypto deposit address.
- Payouts: list supported banks, resolve a bank account name, initiate a payout, list payouts, get payout details.
- FX: live rates; guaranteed, forward and inverse quotes with a 60-second validity window.
- Beneficiaries: corridor requirements, list, save, delete.
- Transactions: list transactions, get a receipt.
- Collections: "10 currencies" across African local currencies, G3 currencies and stablecoins (the page does not name them); dedicated Nigerian NUBAN virtual accounts; multi-chain crypto deposits settled to merchant balances.
- Webhooks signed with HMAC SHA-256, retries; idempotency keys; authentication with secret keys; sandbox.
- Recipient verification against the national banking switch before payouts.
- Global accounts (homepage FAQ): USD, EUR, GBP business accounts with FX built in; receive via ACH, wire, SWIFT, SEPA, Faster Payments. Source: https://tabsglobal.co/

**PROXY (Verto)**: Business Accounts (multi-currency, 11 currency wallets), FX (49 currencies), Corporate Cards (spend from 11+ currency balances), Verto Atlas (embedded API for collections and payouts, for fintechs and platforms). Source: https://verto.co/ and https://verto.co/atlas/

**PROXY (WeWire)**: Payment APIs, Virtual Accounts, Multi-Currency Wallet, Invoicing, OTC Desk, Stablecoin, Treasury, Swift/BIC Checker, Rates. Source: https://www.wewire.com/

## Pricing model

- **Tabs:** Not found. No price list, plan tiers or fee schedule on the site or docs. The homepage demo shows a "0.01%" fee on a 25,000 USD to NGN example. Terms: website figures "are illustrative only and are not binding" and "The rates and fees applicable to a transaction are those confirmed to the customer at the time of the transaction." Sources: https://tabsglobal.co/ and https://tabsglobal.co/terms (Terms last updated October 2026)
- INFERRED: the 0.01% is a demo value, not a price.
- **PROXY (Verto)**, plans per Verto's Spot FX page: Free "$0/month", Lite "$25/month", Emerging (marked Popular) "$50/month", Enterprise "Custom". The same page says "No setup fees, monthly fees, or hidden fees", which conflicts with the plan list. Source: https://verto.co/fx/spot-fx/
- PROXY (Verto), third-party summary for US companies only: FX spread 0.6% Free, 0.5% Lite, 0.4% Emerging; exotic currencies 0.6% to 2% on Free; SWIFT USD 20; wallet-to-wallet free. Not checked against Verto's own pricing page. Source: https://www.finder.com/uk/vertofx-review (search summary, not read in full)
- PROXY (Verto), early revenue model (2021): small FX commission plus 1% on its price-discovery marketplace. Source: search summary of https://techcrunch.com/2021/09/30/vertofx-picks-up-10m-for-cross-border-payments-play-in-emerging-markets
- **PROXY (WeWire)**, from its pricing page: foreign collections and disbursements "0.5% + $20" (Fed Wire), "0.5% + $5" (ACH), "0.5% + $40" (Swift); conversion "1.00%" for USD, EUR, GBP and "1.5% - 5%" for exotics; virtual cards "3.5%" collections, "$5" issuance, "$1" top-up; mobile money collections "1.50%"; disbursements "1% capped at 20 GHS". Source: https://www.wewire.com/pricing

## Markets

- Tabs homepage FAQ names Nigeria (NIP), Kenya (PesaLink, M-Pesa), Ghana (GhIPSS, mobile money), South Africa (PayShap, RTC), Egypt (InstaPay), Côte d'Ivoire (Wave, Orange Money), plus "14 more markets in rollout". Source: https://tabsglobal.co/
- Conflict: the docs name only Nigeria. Source: https://docs.tabsglobal.co/llms.txt . INFERRED: docs may lag the site, or other markets are payout only. Not confirmed.
- Terms: "Not all products, currencies or countries described on the Website may be available at any given time." Source: https://tabsglobal.co/terms
- Currencies named on the homepage: USD, EUR, GBP, NGN, KES, GHS, XOF; "20+ currencies" in the stats strip. Source: https://tabsglobal.co/
- PROXY (Verto): regulated in the UK, US, Canada, Nigeria, South Africa, Kenya, Dubai (DFSA) and Tanzania; accepts payments from 190+ countries; local accounts in 50 countries. Source: https://verto.co/
- PROXY (WeWire): operations in Ghana, Nigeria, Kenya, Uganda, UK, Canada, US, Dubai; payouts to "100+ countries". Sources: https://www.wewire.com/about-us and https://www.wewire.com/

## Claimed scale (unverified)

- Tabs homepage stats: "$100m+" processed, "<5 min" settlement, "99.9%" uptime, "20+" currencies. Source: https://tabsglobal.co/
- Tension: LinkedIn shows founded 2026 and the X account was created 2026-08-25. No source explains the "$100m+". Do not repeat it in copy without confirmation.
- PROXY (Verto): "over $3 billion" volume in 2022 with 70% growth and "over 3,000 clients" as of April 2023, per TechCrunch. Source: https://techcrunch.com/2023/04/05/verto-claims-a-quarter-of-svb-customers-operating-in-africa-are-opening-accounts-on-its-platform
- PROXY (WeWire): "over $2.2 billion in transactions", "3,000+ businesses", "80+ countries", as of 2025-06-09. Source: https://blog.wewire.com/product-updates/wewire-secures-mauritius-treasury-license-to-power-trade-finance-innovation/

## Legal entities and regulatory posture

- Tabs Global Limited: incorporated in British Columbia, Canada, no. BC1605763, business number 790857841BC0001, registered office Suite 207, 5577 153A Street, Surrey, BC V3S 5K7. Tabs and Co Ltd: Nigeria, RC 9676595, "a software technology company". Source: https://tabsglobal.co/terms
- Governing law: Nigerian law, non-exclusive jurisdiction of Nigerian courts; Tabs may also sue in other courts, including British Columbia. Source: https://tabsglobal.co/terms
- "Tabs Global Limited is a financial technology company, not a bank." Services run through "licensed banks and payment institutions that Tabs partners with". No partner, licence number or regulator is named. Source: https://tabsglobal.co/compliance
- KYB covers the business, directors, beneficial owners (25% or more) and authorised operators; sanctions, PEP and adverse media screening; no shell companies or shell banks; customer funds held with partners "separately from Tabs' own operating funds". Data protection cites the Nigeria Data Protection Act 2023. Source: https://tabsglobal.co/compliance
- Footer Security link points to a placeholder; no security certification claimed. Source: https://tabsglobal.co/compliance
- PROXY (Verto): VertoFX Ltd is FCA-authorised as an electronic money institution (Firm Reference 901073); ISO 27001 certified by BSI; US operations via a partnership with Global Innovations Bank. Sources: https://verto.co/fx/spot-fx/ and https://verto.co/
- PROXY (WeWire): FINTRAC-registered Canadian MSB (M22043415); Mauritius FSC Treasury Licence and Global Business Licence; UAE entity; ISO 27001. Source: https://www.wewire.com/about-us . Bank of Ghana sandbox reported by BusinessDay (not read): https://businessday.ng/?p=845273

## Funding

- **Tabs:** Not found. No press release, database entry or announcement located across web searches on 2026-11-13.
- The company X account posted "$5m valuation" on 2026-11-04. It is a quote-post of Revolut's post "$115bn valuation." with 0 likes and 0 replies. Source: https://x.com/TabsNetwork/status/2117939587624382757 (via treg tikhub.x.user.posts). INFERRED: a joke or meme reply, not a funding disclosure. The earlier version of this file showed it without the quoted Revolut post.
- **PROXY (Verto):** $10M Series A led by Quona Capital with The Treasury, MEVP, TMT Investments, Unicorn Growth Capital, Zrosk Investments and P1 Ventures, reported 2021-10-01. Sources: https://ibsintelligence.com/ibsi-news/verto-raises-10m-in-a-series-a-funding-round-for-cross-border-payments/ and https://techcrunch.com/2021/09/30/vertofx-picks-up-10m-for-cross-border-payments-play-in-emerging-markets . TechCrunch 2023 says "over $12 million" raised and Y Combinator backing. A 2025 grant of $1.0M (Milken-Motsepe Prize) is listed by aggregators. A Series B listed by Caplight is unverified. Source: https://au-startups.com/startups/verto
- **PROXY (WeWire):** funding rounds and investors Not found. Visa Africa Fintech Accelerator cohort reported, and a podcast says the CEO is raising a $100M fund (unclear whether it is WeWire's). Source: https://www.buzzsprout.com/2423582/episodes/17646712-he-built-a-cross-border-payment-platform-for-businesses-before-30-ebenezer-ghanney-s-wewire-story

## Team size and leadership

- **Tabs:** LinkedIn "2-10 employees", HQ "Toronto", industry Financial Services, founded "2026", followers not returned. Source: https://www.linkedin.com/company/tabsglobal (via treg)
- Tabs founders and executives: Not found. The homepage has a team photo captioned "The Tabs team in a working session." and no names. Careers and Blog links point to placeholders. Searches on founders, CEO and funding returned nothing for Tabs Global. Sources: https://tabsglobal.co/ and https://tabsglobal.co/blog
- Tabs open jobs: none found (treg blitzapi.jobs.company on its LinkedIn page returned 0 results, free).
- **PROXY (Verto):** LinkedIn "201-500 employees", London, 43,679 followers. Founders Anthony Oduu (CTO) and Ola Oyetayo, founded 2018. Sources: https://www.linkedin.com/company/vertofx (via treg) and https://techcrunch.com/2023/04/05/verto-claims-a-quarter-of-svb-customers-operating-in-africa-are-opening-accounts-on-its-platform
- **PROXY (WeWire):** CEO Eben (Ebenezer) Ghanney. Headquarters Accra, Ghana per its About page; the 2025 licence post says UAE HQ with operations HQ in Ghana. Team in "over 8 countries". Headcount Not found. Founding year Not found (a 2025-06 post says launched about three years earlier). A LinkedIn company page for slug "wewire" returned 404, so the correct slug is Not found. Sources: https://www.wewire.com/about-us and https://blog.wewire.com/product-updates/wewire-secures-mauritius-treasury-license-to-power-trade-finance-innovation/

## Public accounts

- X: @TabsNetwork, bio "Payment infrastructure for Africa", location "Africa", created 2026-08-25, 3 followers, following 24, 2 posts. The posts are the "$5m valuation" quote-post (2026-11-04) and a repost on 2026-10-27 of a user saying "Wow, just discovered @TabsNetwork after they listed on Pairlore". Pairlore was not fetched. Sources: https://x.com/TabsNetwork (via treg crawl4ai.x.user.profile and tikhub.x.user.posts)
- LinkedIn company page https://www.linkedin.com/company/tabsglobal : posts endpoint returned no posts (treg tikhub, 2026-11-13).
- Review sites: Trustpilot, G2 and similar for Tabs: Not found (not searched beyond web search). 
- Demo booking: https://calendly.com/t-tabsglobal/30min . Sign-in: https://app.tabsglobal.co
- Founder personal X and LinkedIn posts: Not found, because no founder is named.

## Spend on this file

treg total for the whole refresh (all six files): $0.02035, measured as balance $0.9952 before and $0.97485 after. Calls: LinkedIn company profile (Tabs, Verto), LinkedIn company posts (Tabs), X profile and posts (@TabsNetwork), Trustpilot (Verto), jobs (Tabs returned 0, Verto 15 rows). Three calls were free (WeWire LinkedIn 404, Trustpilot WeWire failed, jobs for Tabs empty).
