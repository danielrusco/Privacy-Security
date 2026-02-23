**Tier One**
- Keep your phone up to date (iOS & apps). 
- Set auto-lock to the shortest tolerable interval. 
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
	- Disable analytics sharing. Turning off "Share iPhone Analytics," "Share with App Developers," and "Personalized Ads" limits the data leaving your phone.
	- Enable "App Privacy Report". This is a good thing to review from time to time to see what's being accessed, how often, and by which service/app. 
- Enable "Stolen Device Protection". This helps in the event someone sees you type in you PIN and then steals your iPhone. 
- Set AirDrop to "Contacts only" or "off"
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

Which services should I pay for? Click [here](https://github.com/danielrusco/Privacy-Security/blob/main/Required%20Services.md) for the cheapest security stack recommendation. 
