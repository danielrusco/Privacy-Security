# Prompt: A Prioritized Digital Security Roadmap

> Copy everything below the line into your AI assistant of choice. Adjust the persona details to match your own situation before sending.

---

Act as a digital privacy and security expert with current, up-to-date knowledge of both mainstream and advanced privacy practices. I want a prioritized roadmap for improving my digital security and privacy — not an exhaustive encyclopedia, but a sequenced plan where each step is ranked by effort versus payoff.

**My profile.** I am currently in the Apple ecosystem (iPhone, Mac, iCloud), but I am not locked into it. I am technically capable: I'm comfortable self-hosting services, configuring VPNs and DNS, working in a terminal, and — if the case is compelling — migrating to a different operating system entirely (e.g., GrapheneOS on Pixel hardware, or Linux on the desktop). Assume I can handle complexity, but don't assume I *should* take it on; part of what I want from you is honest judgment about when the added effort isn't worth the marginal privacy gain.

**Threat models.** Address all three of the following, and be explicit about which recommendations serve which threat model — many guides blur these together, and I want them kept distinct:

1. **Commercial surveillance** — data brokers, ad-tech tracking, cross-site and cross-app profiling, retail analytics. Treat this as the default adversary most people actually face.
2. **Mass surveillance** — ISP logging, government bulk collection, lawful-access requests to platforms I depend on.
3. **Targeted adversaries** — a motivated individual or organization specifically interested in me (stalker, doxxer, sophisticated attacker).

**Scope.** Cover the full range, from foundational to advanced:

- **Foundations**: password managers, passkeys, hardware security keys, MFA hygiene, end-to-end encrypted backups (e.g., iCloud Advanced Data Protection), encrypted messaging, account-recovery hardening, and which of these matter most against which adversary.
- **Browser and device fingerprinting**: how fingerprinting actually works (canvas, fonts, hardware entropy, behavioral signals), why it defeats cookie-blocking alone, and the realistic options — hardened browsers, Tor Browser, the trade-off between blending in and standing out.
- **Network privacy**: trusted-party VPNs (e.g., Mullvad, Proton) versus Tor versus decentralized mixnets like Nym — what each actually protects against, what each leaks, and when layering them helps or hurts. Include DNS privacy and the limits of VPNs against fingerprinting.
- **Physical-world signal leakage**: what my devices broadcast while I'm out — Wi-Fi probe requests, Bluetooth advertising (including tracker networks like Find My), MAC address randomization and its failure modes, cellular identifiers (IMSI), and ultrasonic/cross-device beacons. What can actually be mitigated on stock hardware versus what requires different hardware or an OS change.
- **Self-hosting**: where running my own services (DNS filtering, file sync, photo storage, password vault, VPN endpoint) genuinely removes a party from my trust chain, and where it just shifts risk onto my own ability to patch and secure things.
- **Operating system choice**: a frank assessment of staying on hardened iOS/macOS versus migrating to GrapheneOS or desktop Linux — framed in terms of *who I have to trust* under each option, not just feature checklists. Include what is genuinely lost in the migration (app compatibility, integrations, convenience features).
- **Financial and identity surface**: virtual cards, data-broker opt-outs and removal services, freezing credit, and minimizing the personal data attached to purchases and accounts.

**Format.** Organize the response as a roadmap in three tiers — **do this week**, **do this quarter**, **do when justified by threat model** — with each item annotated by: the effort required, the threat model(s) it addresses, and what it meaningfully changes. Where the privacy community disagrees on something (VPN versus Tor, app-store apps versus sideloading, MySudo-style services versus self-hosting), say so and explain the disagreement rather than picking a side silently. Flag anything where the landscape changes quickly and your information may be stale, and tell me what to verify before acting.

Avoid fear-based framing. The goal is autonomy and informed choice, not paranoia — I want to understand what each measure buys me and what it costs, so I can decide where on the spectrum I actually want to live.
