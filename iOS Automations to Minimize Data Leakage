# Stop Your iPhone From Snitching When You Leave the House

Your phone is constantly broadcasting. Even sitting in your pocket, it's pinging nearby networks, advertising its presence over Bluetooth, and sending unencrypted traffic through whatever Wi-Fi you're connected to. Most people don't think about this — but once you do, it's hard to ignore.

The good news: iOS Shortcuts let you automate most of the fixes so you don't have to remember to do anything. Leave the house, privacy mode kicks in. Get home, everything goes back to normal. Here's how I set it up.

---

## What's actually leaking

Before jumping into the automations, it helps to know what you're actually defending against:

- **Wi-Fi probe requests** — your phone silently broadcasts the names of every network you've ever connected to. Anyone with the right gear nearby can pick that up.
- **Bluetooth beacons** — retail stores, airports, and venues use BT sensors to track movement. You don't even have to connect to anything.
- **Unencrypted traffic** — on a public or unknown Wi-Fi network, the person running that network can see where your traffic is going.
- **Your MAC address** — a unique ID your phone uses to identify itself on networks. Without protection, it can be used to track you across locations.
- **Background location access** — apps running in the background can grab your GPS coordinates even when you're not using them.

None of this requires a sophisticated attacker. A lot of it is just the default behavior of a phone that hasn't been hardened.

---

## The automations

### Leaving home

**Trigger:** When I leave [home address]

```
1. Turn Wi-Fi off
2. Turn Bluetooth off
3. Connect to Tailscale (or your VPN)
4. Notification: "Privacy mode on"
```

Turning Wi-Fi off kills the probe request problem entirely. Your phone stops advertising SSIDs it knows. Turning BT off stops passive beacon tracking. Connecting to your VPN or Tailscale exit node means your traffic is encrypted before it hits any network you don't control.

---

### Arriving home

**Trigger:** When I arrive at [home address]

```
1. Disconnect Tailscale / VPN
2. Turn Bluetooth on
3. Turn Wi-Fi on
4. Notification: "Home network — VPN off"
```

Your home network is trusted, so there's no need for the VPN overhead here.

---

### Connecting to unknown Wi-Fi

**Trigger:** Wi-Fi connects to [any network not on your trusted list]

```
1. If network ≠ home or other trusted networks
   → Connect VPN immediately
   → Notification: "Untrusted Wi-Fi — VPN on"
```

This is the most important one. The goal is to get encrypted *before* any app sends traffic. If you ever connect to a hotel or coffee shop network before the VPN is up, that window of exposure is real.

---

### Away Focus mode

**Trigger:** Manually, or tied to the "leaving home" automation

```
1. Everything from the leaving home automation
2. Location access set to "While Using" only (via Focus filters)
3. Non-essential notifications silenced
4. Low Power Mode on (reduces background radio activity)
```

iOS Focus modes in 16+ let you attach app-level filters — so when this Focus is active, apps can't grab your location in the background. It's the closest thing to a kill switch for GPS harvesting without fully disabling location services.

---

## The VPN piece

Shortcuts can't natively flip a VPN on or off — Apple locks that down. But there are good workarounds:

**Tailscale (my recommendation)**
Tailscale has native Shortcuts actions: Connect, Disconnect, and Set Exit Node. If you're running a home server or a Raspberry Pi, you can set it as your exit node and route all your traffic through your home IP when you're out. Your traffic looks like it's coming from home, your DNS is your own resolver, and the coffee shop Wi-Fi operator sees nothing useful.

**WireGuard**
If you have a WireGuard profile set up, the WireGuard iOS app has Shortcuts support built in. Connect to your tunnel directly from an automation.

**ProtonVPN / Mullvad / NordVPN**
Most major VPN apps have Shortcuts actions now. Check the app's Shortcuts integration — Connect and Disconnect are usually there.

---

## One-time settings (do these manually)

Shortcuts can't touch these, but they matter:

| Setting | Where to find it |
|---|---|
| Private Wi-Fi Address → Rotating | Settings → Wi-Fi → tap your network → Private Address |
| Limit IP Address Tracking | Settings → Privacy & Security → iCloud Private Relay |
| Per-app location permissions | Settings → Privacy & Security → Location Services |
| Disable Significant Locations | Settings → Privacy → Location Services → System Services |
| Disable Analytics Sharing | Settings → Privacy & Security → Analytics & Improvements |
| iCloud Private Relay | Settings → [your name] → iCloud → Private Relay |

The Private Wi-Fi Address one is easy to overlook but important — without it, your phone uses the same MAC address on every network, which makes it trivial to track you across locations.

---

## How it all fits together

Think of it as layers:

1. **Radio silence** — Wi-Fi and BT off means no passive broadcasting at all
2. **Encrypted tunnel** — VPN or Tailscale means the network can't see your traffic
3. **IP masking** — exit node or Private Relay means destination servers see your home IP, not your real location
4. **App restrictions** — Focus filters stop background GPS harvesting
5. **MAC rotation** — Private Address stops network-level fingerprinting

No single layer is enough on its own. The value is in running all of them at once — and automating as much as possible so you don't have to think about it.

---

## Building the automation

1. Open **Shortcuts** → tap **Automation** → **New Automation**
2. Choose trigger: **Leave** → enter your home address
3. Add actions and chain them in order
4. Turn off **Ask Before Running** so it fires automatically

Repeat with the inverse actions for arriving home. The whole setup takes maybe 15 minutes and then you never have to think about it again.
