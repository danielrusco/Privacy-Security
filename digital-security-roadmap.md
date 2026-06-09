# A Prioritized Digital Security Roadmap

*An answer to the companion prompt, written for a technically capable person in the Apple ecosystem who is open to self-hosting and OS migration. Current as of mid-2026; fast-moving items are flagged for verification at the end.*

The organizing idea throughout is trust architecture: every measure either removes a party from your trust chain, reduces what a party can see, or raises the cost of observing you. Effort and payoff are judged against three adversaries — **commercial** (ad-tech, data brokers, retail analytics), **mass** (ISP logging, bulk collection, lawful access to your platforms), and **targeted** (someone specifically interested in you). Most people's actual exposure is overwhelmingly commercial, so the early tiers weight toward it; the later tiers are where the targeted and mass measures live.

---

## Tier 1 — Do this week

These are the measures with the steepest payoff-per-hour. Nothing here requires new hardware, a new OS, or ongoing maintenance.

**1. Password manager with unique credentials everywhere.**
*Effort: low. Adversaries: all. What changes: credential reuse stops being your single point of failure.*
Every other measure on this list is undermined if one breached password unlocks ten accounts. 1Password and Bitwarden are the mainstream choices; Bitwarden can be self-hosted later (see Tier 3) if removing the vendor from the trust chain appeals. Spend the first session migrating only the accounts that matter — email, Apple ID, financial, anything with a saved payment method — and let the long tail migrate as you log in naturally.

**2. Phishing-resistant MFA on the accounts that anchor everything else.**
*Effort: low (an hour, plus buying two hardware keys). Adversaries: targeted primarily, mass secondarily. What changes: phished or SIM-swapped codes stop working.*
SMS codes protect against opportunistic attacks but fall to SIM swaps and real-time phishing. Hardware security keys (two, so one can live in a drawer as backup) or passkeys on the Apple ID, primary email, and password manager close that gap. The Apple ID supports hardware keys directly. Email deserves the strongest protection of all, because it is the recovery path for everything else.

**3. Turn on iCloud Advanced Data Protection — and rehearse recovery.**
*Effort: low. Adversary: mass. What changes: Apple loses the ability to read most of your iCloud content, which also means it cannot hand that content over.*
ADP extends end-to-end encryption to backups, photos, notes, and most other categories. Two honest caveats: mail, calendar, and contacts remain outside E2EE for interoperability reasons, and metadata (file names, sizes, timestamps) stays visible to Apple. ADP also makes account recovery genuinely your problem — set a recovery key and a recovery contact before enabling it, and store the key offline. Check the "Access iCloud Data on the Web" setting; leaving web access on weakens the guarantee slightly in exchange for convenience.

**4. Make Signal the default for anything that matters.**
*Effort: low. Adversaries: all. What changes: message content and most metadata leave the reach of your carrier and platform.*
iMessage is end-to-end encrypted, but if either party backs up to iCloud without ADP, the keys effectively sit with Apple. Signal sidesteps the backup problem and minimizes server-side metadata by design. Enable a username and turn on phone-number privacy so new contacts never need your number. The real cost here is social, not technical — migrating the three or four conversations that matter is the whole job.

**5. Freeze your credit.**
*Effort: an evening. Adversary: targeted (identity theft). What changes: new accounts can't be opened in your name.*
Free at all three major bureaus, reversible in minutes when you actually need credit, and arguably the single highest payoff-to-effort ratio in consumer security. While you're at it, consider the smaller bureaus (Innovis, NCTUE) for completeness.

**6. Email aliasing for everything non-personal.**
*Effort: low, then ambient. Adversary: commercial. What changes: your real address stops being the join key that links your accounts across breaches and broker databases.*
Hide My Email is built into iCloud+; SimpleLogin and addy.io are the portable alternatives if you'd rather not deepen the Apple dependency. One alias per service means a breach burns one alias, not your identity graph.

**7. Encrypted DNS and a tracker-blocking browser baseline.**
*Effort: low. Adversary: commercial. What changes: your ISP stops seeing every domain you resolve, and the bulk of ad-tech requests never leave the device.*
Point the system at an encrypted resolver with filtering (NextDNS hosted, or Mullvad's DNS), and pick a browser posture: Safari with a content blocker is respectable and blends into the iOS crowd; Firefox with uBlock Origin blocks more aggressively. Fingerprinting — the harder problem — is Tier 2.

---

## Tier 2 — Do this quarter

Moderate effort, some ongoing maintenance, and the first measures where the privacy community genuinely disagrees.

**8. Data broker suppression.**
*Effort: moderate and recurring. Adversaries: commercial and targeted (doxxing). What changes: the people-search and broker profiles tied to your name, address, and phone thin out.*
The regulatory landscape shifted recently and matters here. The federal effort died: the CFPB withdrew its proposed rule that would have pulled data brokers under the Fair Credit Reporting Act, so no federal backstop is coming in the near term. The action is at the state level. California's DROP (Delete Request and Opt-Out Platform) went live for consumer submissions on January 1, 2026 — a single verified request that fans out to the 500+ registered brokers — though brokers aren't required to process requests until August 1, 2026. If you're a California resident, file now and expect results in the fall. Everyone else faces the old choice: manual opt-outs (free, tedious, recurring) or a paid removal service. The honest disagreement on paid services: they save real time, but you hand a new company your identifying details, coverage is incomplete, and brokers repopulate — treat them as a subscription, not a cure.

**9. A trusted-party VPN — used for what it actually does.**
*Effort: low to set up, judgment to use well. Adversary: mass (ISP/network observer), mildly commercial. What changes: your ISP and local networks stop seeing your traffic destinations; websites see a shared IP.*
Mullvad and Proton are the usual recommendations for good reasons: anonymous payment options, audited infrastructure, jurisdictions chosen deliberately. Be clear-eyed about the model: a VPN *moves* trust from your ISP to the provider rather than eliminating it, does nothing about browser fingerprinting, and does nothing about tracking on services you're logged into. The community disagreement — "VPNs are snake oil" versus "VPNs are essential" — dissolves once you index by threat model: against your ISP and coffee-shop networks, they work as advertised; against ad-tech identity graphs, they barely register.

**10. Fingerprinting: blend in or randomize, but pick a strategy.**
*Effort: moderate, mostly conceptual. Adversary: commercial. What changes: cross-site tracking that survives cookie deletion gets harder.*
Fingerprinting composes dozens of signals — canvas rendering, installed fonts, hardware concurrency, screen metrics, audio stack behavior — into an identifier that needs no cookie. The trap is that naive countermeasures (obscure browsers, exotic extension stacks) make you *more* unique. The three coherent strategies: blend into a large crowd (Safari on iOS, where the population is huge and homogeneous), randomize per-site (Brave's farbling approach), or join an intentionally uniform anonymity set (Tor Browser, or Mullvad Browser for the same fingerprint-uniformity without the Tor network). Use a hardened browser for sensitive sessions and an ordinary one for logged-in life; trying to make one browser do both jobs serves neither.

**11. Quiet the radios when you're out.**
*Effort: low to moderate; ceiling imposed by the OS. Adversaries: commercial (retail analytics) and targeted (physical tracking). What changes: your device broadcasts less that's linkable to you across locations.*
On stock iOS: set Private Wi-Fi Address to Rotating per network, prune the remembered-network list (your device probes for them), disable Auto-Join on networks you don't control, set AirDrop to receiving-off, and treat Control Center's Bluetooth/Wi-Fi tiles with suspicion — they disconnect rather than disable; the radios keep murmuring for AirDrop, Find My, and Continuity. Genuinely turning Bluetooth off lives in Settings. The honest limits of stock hardware: the Find My mesh means your powered-off-adjacent device still participates in a global Bluetooth network (a trade-off — it's also your theft recovery), and the cellular baseband identifies itself to towers (IMSI) by design; nothing short of airplane mode or leaving the phone addresses that. Finer-grained control — per-connection MAC randomization, true radio kill — is one of the concrete arguments for the OS migration in Tier 3.

**12. Payment privacy, with the shipping-address caveat.**
*Effort: low to moderate. Adversary: commercial. What changes: merchants stop accumulating your real card number, and card-network purchase profiles fragment.*
Virtual card services give you a distinct number per merchant, which compartmentalizes breaches and lets you kill a card a merchant abuses. Apple Pay's tokenization protects you from the *merchant* seeing your PAN but changes nothing about what your bank and the network see. And for physical goods, the dominant leak isn't the payment at all — it's the shipping address, which no card trick fixes. Locker pickup and package-receiving services are the mitigations when that matters.

**13. Self-hosted DNS filtering as a first self-hosting project.**
*Effort: moderate. Adversary: commercial. What changes: network-wide filtering under your control, removing the hosted-DNS vendor from the chain.*
AdGuard Home or Pi-hole on a small box at home, reachable from anywhere over Tailscale, filters every device you own without a vendor in the loop. This is the right *first* self-hosting project because the failure mode is mild (DNS falls back) and it teaches the maintenance rhythm before you trust yourself with anything load-bearing.

---

## Tier 3 — Do when your threat model justifies it

Each of these is the right answer for some threat models and over-engineering for others. The annotation says which.

**14. Tor — and where mixnets like Nym fit.**
*Effort: low to adopt, real usability cost. Adversaries: mass, targeted. What changes: network-level anonymity rather than mere privacy — observers can't link you to your destinations.*
Tor remains the default for serious anonymity: free, two decades of adversarial scrutiny, and a large anonymity set, with the known theoretical weakness that a sufficiently global passive observer could correlate traffic timing across the three hops. That weakness is precisely what mixnets target. NymVPN, the first production decentralized mixnet (launched 2025), routes packets over five independently operated hops while mixing them with cover traffic and timing noise, which makes traffic-pattern correlation dramatically harder even for a global observer. The trade-offs are real and current: meaningful latency in mixnet mode, a smaller and younger network, no independent no-logs audit yet, and reviewers caught the iOS client silently falling back to a normal connection — exactly the failure mode you can't tolerate if you need this layer at all. Reasonable posture in 2026: Tor Browser for sensitive sessions; watch Nym as the architecture to graduate to if a global-passive-adversary threat model is genuinely yours. Don't casually layer VPN-over-Tor or Tor-over-VPN — the combinations have subtle failure modes and usually you should pick the one tool your threat model names.

**15. The GrapheneOS question.**
*Effort: high, one-time plus adjustment. Adversaries: all, but the strongest case is mass and targeted. What changes: the number of parties you must trust drops; the number of things you must manage rises.*
Framed as trust architecture rather than features: hardened iOS is excellent against external attackers *with Apple as a trusted intermediary* — Apple holds keys for some categories, controls the software supply chain, and answers lawful process. GrapheneOS on Pixel hardware removes the platform vendor from most of the chain: no Google account required, Play services run sandboxed as an unprivileged app if you need them at all, per-app network and sensor permissions, per-connection MAC randomization, USB port lockdown, auto-reboot to keep data at rest, and a duress PIN. What you actually give up: iMessage and the Apple Watch, the ADP-protected iCloud fabric, Shortcuts automations, seamless continuity across your Macs, and occasionally a banking app or contactless-payment path that objects to the OS. The community disagreement is real and respectable: one camp holds that hardened iOS plus ADP is more security than almost anyone needs and the ecosystem cost isn't worth it; the other holds that GrapheneOS is simply the strongest consumer mobile OS and the rest is inertia. The deciding question is honest: is your threat model about *external attackers* (iOS is arguably fine) or about *reducing trusted parties* (GrapheneOS wins outright)? A two-device transition period — Pixel as daily driver, iPhone retained for stragglers — converts a leap into an experiment.

**16. Self-hosting the load-bearing services.**
*Effort: high and ongoing. Adversary: mass primarily. What changes: vendor by vendor, parties leave your trust chain — and you inherit their operational duties.*
The clean decision rule: self-hosting is a win where it *removes* a party that could otherwise read or be compelled to produce your data, and a wash or a loss where it merely shifts risk onto your own patching, backup, and uptime discipline. Strong candidates: Vaultwarden (Bitwarden-compatible vault), Immich (photos — the richest behavioral dataset most people hold), Syncthing or Nextcloud (files). Keep everything behind Tailscale rather than exposed to the internet, and hold yourself to the 3-2-1 backup rule, because the most likely adversary for a self-hosted stack is not the NSA — it's your own dead disk. Note that some of this is moot if ADP already covers it end-to-end; the marginal case for self-hosting photos *against Apple* is thinner once ADP is on, and rests on metadata and supply-chain trust rather than content access.

**17. Lockdown Mode and the genuinely-targeted tier.**
*Effort: low to enable, real friction to live with. Adversary: targeted (mercenary spyware).*
If your situation plausibly includes commercial spyware — journalism, activism, certain litigation — Apple's Lockdown Mode meaningfully shrinks the attack surface (message attachments, web fonts, link previews, unknown FaceTime calls). Beyond that lies the tradecraft tier — travel devices, leaving the phone at home, Faraday sleeves — which is the correct answer for a small number of people and theater for everyone else.

---

## Verify before acting

The landscape moves; check these rather than trusting this document's snapshot. **California DROP**: broker processing obligations began phasing in August 1, 2026 — confirm current status and whether your state has launched anything comparable. **NymVPN**: whether an independent no-logs audit has landed and whether the iOS fallback behavior is fully resolved. **GrapheneOS**: currently supported Pixel models, the state of sandboxed Play compatibility with your specific banking and payment apps. **iOS settings**: names and locations shift between versions — confirm Private Wi-Fi Address modes and the current behavior of Control Center radio toggles on your installed version. **VPN providers**: date of each provider's most recent infrastructure audit.

## Where to stop

A reasonable person can stop at Tier 1 and be better protected than the vast majority of the population. Tier 2 is where someone who cares — and you evidently do — should land. Tier 3 is not a destination but a menu, and the discipline is matching items to the adversary you actually face rather than the most interesting one. Every measure costs something in convenience, social friction, or maintenance; the point of the threat-model framing is that you get to decide, soberly and per-item, which costs purchase something you value. Privacy work done well doesn't feel like hiding. It feels like deciding who gets to know you.
