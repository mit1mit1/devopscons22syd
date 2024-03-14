# Sort Your Shift (Left) Out - Anthony Rees, Regional Security Solutions Engineer, Lacework

Make sure you go thank the organiser for bringing all of this together afterwards, that's always underestimated. And it's important, it's really important to bring like-minded people together, and it's been a couple of tough years on that front.

Who am I? I security engineer for a security company called Lacework, I can be followed on twitter or github at anthonyrees.

Storytime. Before DevOps, we used to run absolutely enormous pieces of work, and try to get them delivered in a year or two. There was no fail fast - you weren't allowed to use the word fail.

This picture is from Woodstock, where they tore the tower down. Before we had DevOps, where we "brought the wall down", we did something a bit like Aerosmith with "Walk this way", we brought together the operation and development team. That conversation, or lunch together, was good and important, but it wasn't far enough. We then had to get DevSecOps (like Live Aid). It was the only way to survive as a movement. It's a direction we're heading in, and we need to bring even more together.

I was thinking of all these ideals we have when I decided to do this talk (look, I just picked shift left because it fit in the title):

(Say "Shift Left" again, I dare you)

DevSecOps, Shift Left, Containers, Agile, Docker, SRE, K8s, Microservices, DevOps - Bingo?

Some people use these words without understanding the meaning, let alone how to implement them in your organisation, let alone at scale.

Definition: "Shift Left" is to take a task that's traditionally done at a later stage of the process and perform that task at earlier stages.

I do love the State of DevOps report (my only issue with it is that it isn't APAC focussed). Stats I loved from the 2021 report, about Elite vs Low performers: over 900x faster deploy rate.

Containers are being moved towards as the target deployment of choice.

But what about in Australia/New Zealand? We have the Lacework ANZ Survey. We had a fair few people, who were a bit of a mixed bag.

How often do they release? Interestingly, 2% never release (lol).

A good third had experienced major shift left changes, 11% had no plan to shift left.

Main obstacles to implementing shift left - budget is the biggest one.

Who is responsible for security in your responsibility (43% security, 18% operations, 10% developers, 29% all of the above).

Is current security a blocker to DevSecOps? 63% said yes.

What can we use to do things better? Glad you asked. Here are some of my favourites.

In the container world, we have industry frameworks - 4Cs.

Cloud industry has recommended architectural frameworks - keep looking back at these, sometimes we forget.

AWS - Well Architected framework
Azure - Well-Architected framework
Google Cloud -Architect frameworks

What are the best in the industry using to improve?

IaC code scanners.

Cloud compliance as code (use industry compliance controls such as CIS, NIST, PCI DSS, which can be turned into code and run against your code continuously to ensure you're not just compliant when the auditor is in the office).

Careful code copy - Stack Overflow has produced some marvellous bugs over the years, do your due diligence when copy pasting it.

Cloud logs - make sure they're switched on, it's a small price to pay (well, sometimes it is, but it's sure worth it).

Admission controllers.

Configuration as Data is an emerging cloud infrastructure management paradigm. You can configure policy as code to make sure containers you don't trust never end up in production.

Container vulnerabilities. Scan your containers at build and in the image repository for CVE's, packages, severity. You need to ensure the code you've copied off the internet is safe to run.
