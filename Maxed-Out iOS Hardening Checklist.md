
*A setup sequence, ordered from foundation upward. Work through it top to bottom — later layers assume the earlier ones are in place. Tradeoffs are noted inline so you can decide what's worth the convenience cost.*

*Current as of iOS 26.5 (June 2026). Apple shuffles menu paths between versions; if a path has moved, search the setting name in Settings.*

---

## 1. Foundation — hardware and OS

- [ ] **Use iPhone 17-class hardware if maxing out.** It ships Memory Integrity Enforcement (always-on memory tagging) and is currently exempt from the low-level forensic extraction that still works against most older iOS 26 devices. This is the biggest single lever, not an optional extra.
- [ ] **Keep iOS fully current.** Settings → General → Software Update → turn on Automatic Updates *and* Security Responses & System Files. Background security patching shrinks the attack window even when you delay a full update. The unpatched gap is almost always the real risk.
- [ ] **Set a long alphanumeric passphrase.** Settings → Face ID & Passcode → Change Passcode → Custom Alphanumeric Code. This is the root of all device encryption — the Secure Enclave entangles it into your keys, so passcode strength *is* your brute-force resistance. Biometrics ride on top for convenience; they don't replace it.

---

## 2. Account and encryption

- [ ] **Advanced Data Protection ON.** (Already done.) End-to-end encryption across nearly all iCloud categories — Apple can't read it or hand it over.
- [ ] **Register two hardware security keys for your Apple Account.** Settings → [your name] → Sign-In & Security → Add Security Keys. FIDO2 keys (e.g. two YubiKeys) replace SMS/phone-number recovery and kill SIM-swap and Apple ID phishing in one move. Highest-impact, most underused setting Apple offers. *Tradeoff: lose a key and you lean on your recovery key, so keep that safe.*
- [ ] **Set a recovery key and store it offline.** Settings → [your name] → Sign-In & Security → Recovery Key.
- [ ] **Consider dropping recovery contacts** if you want to minimize the recovery attack surface. *Tradeoff: higher lockout risk — only do this if you're confident in your key and passphrase backups.*
- [ ] **Migrate logins to passkeys** where supported. A phished passkey is worthless to an attacker; iOS 26 nudges automatic password-to-passkey upgrades.

---

## 3. Anti-theft, anti-coercion, forensic resistance

- [ ] **Stolen Device Protection → Always.** Settings → Face ID & Passcode → Stolen Device Protection → Require Security Delay: Always (not just "away from familiar locations"). Forces Face ID plus a one-hour delay for sensitive changes even if someone has your passcode.
- [ ] **Disable accessory data access when locked.** Settings → Face ID & Passcode → Allow Access When Locked → Accessories OFF. Blocks GrayKey-style USB forensic tools against a locked phone.
- [ ] **Strip the lock screen.** Same menu — turn off Control Center, Siri, Wallet, Notification Center, Reply with Message, and Today View access while locked. Minimize what's reachable without unlocking.
- [ ] **Erase Data after 10 failed attempts.** Bottom of Face ID & Passcode. The closest iOS gets to an automatic wipe. *Note: there's no duress-PIN equivalent on iOS.*
- [ ] **Know that reboot resistance is automatic.** iOS reboots after inactivity and after certain patches, flushing RAM-resident spyware and returning the phone to its locked, keys-not-in-memory state. Nothing to toggle — just don't disable it, and reboot manually now and then.

---

## 4. Network and tracking

- [ ] **App Tracking Transparency off at the source.** Settings → Privacy & Security → Tracking → turn off "Allow Apps to Request to Track." The answer is now always no.
- [ ] **Kill Apple's own telemetry.** Privacy & Security → Analytics & Improvements → disable all. Privacy & Security → Apple Advertising → Personalized Ads off.
- [ ] **Rotating Private Wi-Fi Address.** Settings → Wi-Fi → (network) → Private Wi-Fi Address → Rotating. Defeats MAC-address fingerprinting across networks.
- [ ] **Safari tracker defenses.** Settings → Apps → Safari → enable Prevent Cross-Site Tracking, Hide IP Address from Trackers, Fraudulent Website Warning.
- [ ] **Encrypted DNS.** Install a NextDNS or Mullvad DNS configuration profile for query privacy plus filtering.
- [ ] **Real VPN for untrusted networks.** Mullvad or Proton for egress; Tailscale for your personal mesh.
- [ ] **iCloud Private Relay on**, but treat it as partial — Safari and some traffic only, not a full tunnel.

---

## 5. App and data surface

*This is where iOS gestures at GrapheneOS's scoping without fully delivering it.*

- [ ] **Photos → Selected Photos** per app, not full-library access. Nearest analog to Storage Scopes.
- [ ] **Contacts → share a subset** per app (iOS 18+). Nearest analog to Contact Scopes.
- [ ] **Location → While Using or Never** per app; turn off Precise Location where it isn't needed.
- [ ] **Disable Significant Locations.** Privacy & Security → Location Services → System Services → Significant Locations off. Trim the other System Services location toggles while you're there.
- [ ] **Audit Microphone, Camera, Local Network, Bluetooth** grants per app.
- [ ] **Read the App Privacy Report.** Privacy & Security → App Privacy Report. Shows what apps actually touch versus what you assumed.
- [ ] **Hide My Email aliases as a discipline** — a unique address per service. Structural compartmentalization: a breach or broker leak can't correlate you across accounts.

---

## 6. De-feature pass

*Every capability is attack surface. Remove what you don't use.*

- [ ] **Decide on Apple Intelligence.** Complex requests go to Private Cloud Compute — stateless, audited, request deleted after processing, and genuinely the strongest mainstream cloud-AI posture. Still remote inference, though. For on-device-or-nothing, toggle it off in Settings → Apple Intelligence & Siri.
- [ ] **AirDrop → Receiving Off or Contacts Only.** AirPlay receiving off. Bluetooth off when idle.
- [ ] **Remove unused apps.**
- [ ] **Never install an untrusted configuration or MDM profile.** The single biggest self-inflicted backdoor on iOS — far more dangerous than anything in the App Store.

---

## 7. Nuclear option — Lockdown Mode

- [ ] **Trial Lockdown Mode for a week.** Settings → Privacy & Security → Lockdown Mode. Disables browser JIT, strips risky message attachment types, blocks unknown FaceTime calls, and closes the zero-click surfaces mercenary spyware relies on. *Tradeoff: some sites and attachments break; you'll allow trusted domains by hand.* Overkill for most; the switch you flip the moment your threat model includes a targeted adversary.

---

## 8. Operational discipline

*The part no setting covers.*

- [ ] Reboot regularly to flush memory.
- [ ] Don't tap unexpected links.
- [ ] If you suspect targeting, run iVerify or Amnesty's Mobile Verification Toolkit (MVT).
- [ ] For travel into a hostile jurisdiction, carry a clean device with a separate Apple Account, not your daily driver.

---

## The residual gap vs. GrapheneOS

No iOS toggle closes these, by design:

- No per-app network kill (you can't fully revoke internet from an app)
- No sensor blocking (gyroscope, compass, barometer stay exposed)
- No true storage/contact *spoofing* — only Apple's limited subset-sharing
- No duress PIN
- No isolated user profiles
- Apple still sits in the loop by default

What you get in exchange: configured this way on current hardware, you're about as hard a consumer target as exists against external attackers — remote exploits, spyware, forensic extraction, theft. The gap is agency over your own information environment, not resistance to outsiders.
