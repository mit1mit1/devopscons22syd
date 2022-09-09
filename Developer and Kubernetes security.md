# Developer and Kubernetes security: code to cluster with Snyk - Pas Apicella, Snyk

Most devs are using open source libraries - that presents a risk.

We want to deploy our code, sometime we use VMs, more often than not we use containers. We need to know when those containers have vulnerabilities.

- Infrastructure as code - misconfig here is #1 possible vulnerability.
- Code itself - we want to find and fix bugs here during Dev not testing.
- Cloud sec posture management.

Snyk is aimed at dev time checks, Systic is better for monitoring deployed containers.

Live app deployment and scanning demo, starting now.

Hosts: Lawrence and Pas from Snyk (solutions engineering team)

# Workshop

## Snyk Primer

Modern applications look like:

- App code (10/20% of the code, deployed daily).
- Open source libraries (80% of code which contains 80% of vulnerabilities)
- Containers (docker/kubernetes, etc.)
- IaC (#1 cloud vulnerability is misconfiguration here)

Snyk is going to scan code for vulnerabilities. It breaks down into the same 4 sections:

- synk code for app code
- snyk open source for libraries
- snyk container for container registry scanning or kubernetes cluster scanning
- snyk IaC for coding terraform files, etc. from source).

It has (according to its employees) a good API, dev experience (upgrades deps for you if you accept suggested changes, etc., at enterprise level can set policies at a governance level).

## Snyk CTF Event

We’ll have 5 challenges, easy to hard, they can be done in any order.

Click on the links available under hints and take down notes for useful stuff (some hints cost points).

You’ll have access to the source code.

Tags on the challenge will point you to the right path to take.

Use google (duh).

Github stuff can be imported into snyk.

Your aim is to find the flag, which means you have to find a way to hack the application. HTTPie, curl, Postman will all be helpful.

## The Challenges

The other challenges involved:

- Taking advantage of an exploit in a file system library to query "/public/../../" and reveal files outside of the public folder.
- Taking advantage of a mongoDb injection opportunity in source code.
- A PHP vulnerability with DB injection (written up at https://snyk.io/blog/toplang-ctf-snykcon-2021-explained/).
- A log4j vulnerability on an Apache tomcat container that can be used to execute arbitrary java files on the server..

Challenges started off with only one or two vulnerabilities (as per the snyk analysis) so it was easy to know the best way to exploit, but got increasingly more red herrings. The solutions involved just postman/curl at first, but the last couple needed SQL/nosql/script writing for injection too. That said, most of the solutions were close to something you could find online (snyk came with example exploits for some of them too).

For open source exploits, you still had to look at the source code to see how the library was used to exploit it (obviously you could tell a real hacker would be able to guess/brute force the way to exploit).

## Takeaways

It was definitely fun, in my opinion. Going through a meta-compliance course gives a decent example of how some exploits work, but a CTF made it more real.

It also made snyk look pretty nice. Of course, it was a controlled environment, by snyk, so it was always going to. I'd like to try snyk on a couple of real, large applications to see how the level of white noise/suggested fixes that actually work compares to alternatives in the space.
