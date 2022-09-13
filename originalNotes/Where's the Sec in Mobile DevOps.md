# Where's the Sec in Mobile DevOps? - Pat Shueh, VP, Solutions Engineering at Zimperium

Mission: protect one mobile device/app at a time.

Two school of thoughts.

DevSecOps:

- AppSec in the pipeline
- Automation (SAST, DAST, SCA)
- App Harden/Anti-Tampering
- Security Training / Awareness
- Pen testing before go live.

This is perhaps too much of a focus on pre-production - what about production?

SecDevOps:

Zimperium/Pulse did a survey on best practices in mobile apps, but is was fairly small as it is a smaller field then devops.

Biggest challenges with deploying mobile application security and protection solutions to date? Number one response was that UX suffers.

Which tasks were people most concerned with?

1.  Securely storing and transmitting data
2.  Using proprietary source code.
3.  Using 3rd party SDKs (how do you know what 3rd party libraries actually do)?

MASVS - Mobile App Security Verification Standard (evolution of OWASP Top 10 for Mobile). It's pretty good at giving advice based on the actual type of app you are working on.

Most people are pretty good at testing source code with static scanning. They don't test the app binary as a whole after it is built (Pen testing should go here - but often Pen testing is last step after building, we need something for continual feedback during development).

This is like checking the ingredients before cooking, but not tasting it after.

Once the app is released, how do you know if it's on fire? Do you have security related observability feedback? How many people are using your app on a compromised device? How many people are hooking into it with potential malware?

From the survey, people believe the greatest risks are:

1. Malware on the user device.
2. Phishing, reverse engineering, rogue wifi network communication or running the app on jailbroken devices (all fairly even).

You mobile app is running on devices you have no control over. It tends to be make like a vault, hardened, encrypted and obfuscated, but often opened inside a house that is a flimsy wooden thing. Compromised devices with exploits of outdated OSs, tampering, malware or trojans are a thing. You cannot assume that the device your app is running on is behaving correctly - you must assume the device is potentially compromised.

E.g. When you load encryption key into memory, it gives stuff away as clear text if the attacker has access to memory.

Right now, if your app is on the public google play/i-App Store, anyone can get the binary and do what they want with it.

App Risks seen on the google play/apple store:

- No code protection (81% on Android, 68% on Apple)
- Lot of other bad numbers.

Open Source R8/Proguard is from google, an interesting trick to rename functions and variables for a slight increase in obfuscation (rename variables and classes). But strings and stuff will be there still, so it's usefulness is limited.

If keys are available in the app, that's a big issue too.

Obviously, there's no need to obfuscate everything either. But it is a good slow down for the attacker.

SecDevOps - work with security from the get go.

Any application with certificate pinning will have the certificate inside the application. Attacker can tamper with it - it needs to be protected.

Until here, we've assumed the attacker has just downloaded the application and looked at the binary without running it.

Now, if the attacker runs the app on a rooted device, things can go wrong too. E.g.

1. Compromise the device
2. Bypass the runtime mitigation.
   ..
3. Get sensitive data

Attackers have good tools, devs have only half-decent tools.

Mobile devices have a challenge with key protection. The key is in memory, and memory might be compromised. Jailbroken devices can dump keychains, which might even be in usable text.

Moral of the story, assume the device is compromised.

An example solution:

Use whitebox encryption instead of traditional encryption.

Challenges:

- Bypass Tools Updates Frequently - up to 10 commits in one week
- Difficult to keep up with the changes (not building a security tools)
- Risk of false positives.
- What about tampering / code injection / memory dump / ssl / bypass?
- What about security telemetry/feedback loop?

Don't just check for root and jailbreak - it doesn't have to be an end game. Your app should still be safe even on a jailbroken device.
