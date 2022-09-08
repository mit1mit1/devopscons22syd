# Leverage 'Ahead of Time' Intelligence to Tackle Supply Chain Vulnerabilities - Michael Fowler, Technical Account Manager at Checkmarx

It was once a possibility for open source libraries to be compromised. Now it happens increasingly frequently - to the point that the American government have put out an executive order about it.

Supply chain Levels for Software Architects (SLSA) are some big players coming together to try and regulate source threats, build threats and dependency threats in the supply chain.

Source and build threats are old hat to fix, but dependency is a newer issue. Everyone is using open source - 90% of your code is probably open source normally. But...

Say a dev asks for an open source package - that package uses other open source packages, which installs other open source packages - sometimes hundreds.

Monthly package releases are increasing on a bunch of platforms (except for ruby). You could try and avoid open source, but let's be real, everyone is using it now, the efficiency boost is too much to give up.

We trust OS so much because:

- anyone can look
- if there's an issue "someone" will notice (but do they)?
- there's scoring mechanisms to star and rate (but starjacking is a thing)

This contributes to trustworthy feeling, but it can go bad.

E.g.:

ua-parser-js - actively maintained for 10 years, millions of regular downloads, most likely you're already using it (facebook is).

It didn't have 2FA on the account, a Russian hacking group got it, published to credentials, and they installed crypto miners on many many devices.

E.g. 2 weeks later:

coa and rc, 22 million weekly downloads. We don't know how, but somehow the same malicious code got put into both of them.

You can ensure your devs have 2FA, but you can't ensure the hobby developer who makes some little library that's part of React does too.

E.g. 3:

riaevangelist, another super popular library. The author put some very obfusicated code into the library. It turns out that it checks your IP, and if you're from Russia or Belarus, it deletes - everything.

The author was asked about it, he said "It's my code, you're running it, I can do what I want with it".

He did this to one of his projects, he has 40 others, what if he decides he just doesn't like big banks?

E.g. REDLILI:

These guys are a supply chain attack threat. They create malicious packages from all different accounts, on disposable domains - so they can't be caught.

What to do?

Align security and operations:

- Frame the conversation about open-source usage with dev and management
- Understand your open source risk profile.

(Insert Checkmarx advertising spiel - seems a similar tool to Snyk, scans and alerts you to vulnerabilities in packages and subpackages, gives you attack vectors - see slides or their website at https://checkmarx.com/ for this).

Vulnerable != Malicious.

- It's okay to run vulnerable code, as long as it is managed and triaged.
- It's not okay to run malicious code.

Checkmarx also claims to keep the open source libraries up to date on found vulnerabilities, which seems cool.
