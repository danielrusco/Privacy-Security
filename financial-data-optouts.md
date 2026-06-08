# Financial Data Opt-Outs Actually Worth Filing

A short, prioritized reference. The goal is to file the handful of things with real payoff and skip the theater. One insight belongs up front, because it determines what's even possible.

Transaction data sits behind a legal wall that most privacy laws don't reach. Banks and card issuers are governed by the Gramm-Leach-Bliley Act (GLBA), and the comprehensive state privacy laws — the CCPA and its roughly nineteen siblings — almost all *exempt* GLBA-regulated financial data. In practice that means a California-style "delete my data" request generally cannot force a bank like Citi to erase a customer's transaction history; that path is closed by design. Leverage at the *source* is limited to narrow GLBA and FCRA opt-outs. The real leverage is **downstream**, on the data-broker layer, plus minimizing what enters the system in the first place. And the federal backstop just got weaker: the CFPB's planned rule to bring data brokers under the Fair Credit Reporting Act was withdrawn in May 2025, so there's no incoming federal constraint to wait on.

What follows is ranked by payoff per unit of effort.

## Tier 1 — High payoff, file these

**Prescreened credit and insurance offers — OptOutPrescreen.** This is the single highest-leverage filing. It stops the credit bureaus from selling consumer files to issuers for "pre-approved" mailers, one of the cleaner pipes feeding a financial profile into marketing. The mechanism is 1-888-5-OPT-OUT (1-888-567-8688) or optoutprescreen.com. Five years online; permanent if the signed form is mailed. It's FCRA-backed, so it actually binds.

**Data-broker deletion — the downstream layer with the most reach.** This is where transaction-derived profiles get fused with location and demographics and resold, and it's reachable by state law even though the bank itself isn't.

For California residents, the Delete Act and its DROP system are the one-stop mechanism privacy advocates spent years asking for. The Delete Act creates a centralized deletion platform, with registered data brokers obligated to honor deletion on an ongoing basis beginning August 1, 2026; if a broker can't verify a request, it must opt the person out instead. One submission propagates to every registered broker and keeps working — by far the best return on effort available to anyone who qualifies.

Outside California, there's no one-stop button yet. The equivalents are the state data-broker registries — Vermont, Oregon, and Texas each maintain one alongside California, each with several hundred registered entries — worked through individually, plus direct opt-outs at the large aggregators (LexisNexis Risk Solutions, Acxiom, Epsilon, CoreLogic). Done by hand, this is genuinely tedious.

Either way, a removal service (Optery, Incogni, or DeleteMe) automates the recurring broker-deletion grind. For non-California residents especially, it's usually worth the subscription purely on time saved, since brokers re-list and deletions have to be re-sent on a cycle.

## Tier 2 — Narrow but real, file once

**GLBA "nonaffiliated third party" opt-out, per institution.** Every bank and card issuer sends an annual privacy notice carrying an opt-out for sharing nonpublic personal information with *unaffiliated* companies. It's worth filing with each issuer. The limits matter, though: it does not cover sharing with affiliates, with "service providers," or under "joint marketing" arrangements, and it doesn't touch data the network frames as aggregated or de-identified. It closes one specific pipe, not the main ones. Low effort, so still worth doing — just not to be mistaken for the whole job.

**FCRA affiliate-marketing opt-out, per institution.** Separate, and often buried in the same notice: this limits a financial company's *affiliates* from using shared information to market. It's a different lever from the GLBA opt-out (affiliate versus nonaffiliate), worth toggling at the same time.

**Card-network data opt-outs.** The networks run the wholesale monetization. PIRG has documented Mastercard selling transaction data through third-party marketplaces and its in-house Data & Services division; American Express sells through the analytics firm Wiland, while Visa shut down its private data-selling operation in 2021. Mastercard and Amex publish data and marketing opt-out pages; they're obscure, and the networks frame much of this as "anonymized" (which the re-identification research shows is leaky), but the opt-outs exist and cost nothing to file.

## Tier 3 — Optional cleanup

**DMAchoice**, run by the ANA, trims direct-mail marketing across participating senders. Small fee, modest effect, set-and-forget. Marginal next to Tier 1, but cheap.

## What none of this fixes — so plan around it

The bank and card network still see every transaction in full. No opt-out changes that; it's the cost of using the rail. The only way to keep a transaction out of that view entirely is to not put it there — cash, cash-bought prepaid, or the Monero-to-gift-card bridge.

"Anonymized" and "aggregated" network sales largely sit outside these opt-outs, and transaction data resists real anonymization: a few time-and-place data points re-identify most people in a card dataset.

State comprehensive laws exempt GLBA-governed bank data, so effort spent trying to CCPA a transaction history out of an issuer is wasted; that energy belongs on the broker layer instead.

## The honest priority order

Three actions capture most of the realistic gain: OptOutPrescreen; broker deletion (the Delete Act's DROP platform for Californians, a removal service for everyone else); and the GLBA plus FCRA opt-outs at each issuer. Everything below that is cleanup. The largest lever of all isn't a filing at all — it's shaping what enters the system at payment time, which is the subject of the companion piece on payment methods.
