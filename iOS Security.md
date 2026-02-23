**Tier One**
- Keep your phone up to date (iOS & apps). 
- Enable Advanced Data Protection - protects any iCloud data on Apple's servers. 
- Install an adblocker ([AdGuard](https://adguard.com/en/adguard-ios/overview.html)) for your browser. Safari is pretty secure with adGuard, but Brave is also a good browser with built in anti-tracking features. 
- Use a password manager ([BitWarden](https://bitwarden.com/download/)) and don't reuse passwords. 
- Use an encrypted messaging app ([Signal](https://signal.org/download/)). 
- Enable 2FA on all accounts that use it ([Ente Auth](https://ente.io/auth/) and [2FAS](https://2fas.com/auth/) are good open source TOTP apps, a [YubiKey](https://www.yubico.com/store/) is a great physical 2FA option). Avoid SMS based 2FA, as it's the least secure. 

**Tier Two** 
- Delete any app that can be accessed through the browser (Amazon, Facebook, etc.). Social media apps, free games, and non-Apple big tech apps (Office365, Gmail, etc.) are all worth deleting. [Proton](https://proton.me/) is a great alternative to Gmail/Gsuite. 
- Review each item in the “Privacy & Security” settings, only enable access to necessary functions (e.g. location services for maps apps). There are some good YouTube tutorials on what settings to disable/keep enabled (Privacy Guides, Techlore, & PayetteForward). 
	- Disable Siri suggestions and Siri & Search access per-app. 
	- Review what can be accessed via the lockscreen. 
	- Make sure "disable USB accessories when locked" (Settings → Face ID & Passcode → Accessories) is enabled. This provides protection against hardware-based attacks (like Cellebrite) and is less disruptive than full Lockdown Mode. 
- Run all your traffic through a VPN ([Obscura](https://obscura.net/) or [Mullvad](https://mullvad.net/en), [iCloud Relay](https://support.apple.com/en-us/102602) in a pinch). This can’t protect against fingerprinting, but does keep your traffic somewhat anonymized from your ISP/carrier. 
	- Configure your VPN to use a privacy-respecting DNS resolver (NextDNS, Quad9). You can also set this up in your general DNS settings so that your DNS is secure even when not using a VPN. 
- Use a privacy-focused email alias service. [iCloud+](https://support.apple.com/en-us/108047) has this feature, but you can also use [SimpleLogin](https://simplelogin.io/) or [Addy.io](https://addy.io/). The "Mail Plus" version of Proton allows for up to 10 email aliases, the "Proton Unlimited" version of Proton is ... unlimited. 
	- Non iCloud+ email alias services allow you to use an email alias for your Apple ID that's not used anywhere else, which helps protect your AppleID from being compromised. If you're good about not using the same password twice, you probably don't need to worry if you iCloud email is your actual email. 

**Tier Three**
- Disable WiFi & Bluetooth when not at home (you can setup an automation in Shortcuts to do this). 
- Enable "Lockdown Mode". 
- Disable location services altogether. 
- Use a PIN instead of Face ID (6+ characters). FaceID is very secure, but you can be forced to unlock your phone with FaceID. 
- Power down your phone before going through security. When powered down, the phone is in its "Before First Unlock" state which means the secure enclave hasn't decrypted the keychain yet, making forensic extraction significantly harder. 

**Tier Four** (a.k.a. Tin Foil Hat Mode)
- Keep your phone in a faraday sleeve when not in use. Yes, literally wrap your phone in tinfoil to keep the 5G out. 
- Use an eSIM as well as a carrier with minimal data retention. Mint Mobile & Visible don't require "Know Your Customer" verification. Neewer companies like [Phreeli](https://www.phreeli.com/ ) and [Cape](https://www.cape.co/ ) are marketed as privacy focused carriers, but don't have long track records. They offer increased metadata privacy that Mint & Visible don't. 


**Privacy Isn't Free**

Cheapest Diverse Stack - $10.87
- $0.99 iCloud+ subscription for email aliases
- $3.99 "Mail Plus" Proton subscription
- $5.90 Mullvad VPN subscription 
- $0.00 BitWarden account 

Cheapest Siloed Stack - $9.99
- Proton Unlimited subscription, which covers email aliases, email services, VPN, & password manager. Downside is that all you eggs are in one basket. Bonus is that you also get 500GB of encrypted storage vs only 50GB with iCloud+, which is only encrypted if "Advanced Data Protection" is enabled. 

What I Currently Use - $13.71
- $2.99 iCloud+ subscription for email aliases, will be trying to downsize to the $0.99 plan once I clean out my iCloud storage. I really like how easy it is to setup new email aliases on my iPhone. However, it's much more tedious on my MacBook. Since I started with iCloud+ aliases, it's not worth it to me to switch to a dedicated alias service at this point. 
- $3.99 "Mail Plus" Proton subscription. I bought a yearly subscription when it was on sale, so my monthly price is lower by 20-25%. 
- $5.90 Mullvad VPN subscription. Bonus: one of my Mullvad devices is my router, so all home network traffic is tunneled through Mullvad. Speaking of routers, I'm a big fan of [GLiNet](https://www.gl-inet.com/) routers. They're simple to use and have VPN (including Tailscale) & AdGuard integrated into their interface. 
- $10.00/year BitWarden account, because I want to support BitWarden. I don't need or use the extra features. 
- I plan to test out Obscura as a VPN to see if I like it over Mullvad. It's basically like Mullvad + iCloud Relay at the same time, which makes it impossible for Obscura to see your data. Pretty cool. 
