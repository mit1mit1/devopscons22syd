# Applying SRE principles to CI/CD - Mel Kalfuss, Senior Developer Advocate of Buildkite

Note: The whole talk has slides based on windows opening in a really old apple macintosh theme, which was hilarious.

## Part I - the Drama

If we don't have drama we're probably not shipping hard enough (GoT theme plays in the background). So let's go through a 'hypothetical' dramatic scenario.

We have monolithic codebase, gargantuan test suite, and microservices as far as the eye can see. That's the hella complex world we live in

Today is the VIP launch date: our branch is green, we're ready to go. Let's make it so (I've always wanted to say that).

But my build failed! What's going on? A test, unrelated to the code I pushed, failed after I merged in. I'm blocked now, and heading into a rabbit hole. This isn't good. I like CI/CD, but I want it to be as boring as possible.

That shouldn't be too much to ask, but it seems it is.

At least Buildkite gives a retry failed step button. But in this (hypothetical) scenario, I'm tapping that retry button like a mechanical-water-drinking-bird to no avail.

Flaky tests are a thing. I know that because of the sheer quantity of memes about them. And knowing they exist in your codebase changes how you look at CI/CD - you end up assuming flakiness whenever a test fails and smacking retry. And you end up misusing CI/CD.

Over a 1 month period, buildkite users spend a cumulative 9413 pipeline days on retrying flaky builds. Big time and money lost.

If course we do enjoy reading social media during these retries. But it definitely gets us out of the flow. Not to mention the disheartening effect of asking on slack "Hey, anyone know if this test is flaky?"

## Part 2: Get out of the hole

SRE - first defined in Google's book, which first defined DevOps as a loose set of practices, guidelines and culture designed to break down silos in software engineering, operations, networking and security.

- Remove silos
- Understand accidents are normal
- Embrace gradual change
- Embrace tooling and culture interrelated
- Measurements are critical

DevOps is about keeping the ecosystem healthy. SRE is more like a job description, keeping that ecosystem healthy by:

- Working towards automation, reducing repetition
- Reducing latency
- Avoiding more reliability than strictly necessary

So, we're in an SRE shaped hole, how do we get out?

Things feel really bad, but is it really bad? What do we actually know?

Measurement is critical to success. Need metrics to found conversations that lead to agreement - need hard data to back up solid decisions.

It is difficult to do a job well without defining 'well'. That's what SLO (objectives) and SLI (measurable indicators tied to the objectives) are for.

Error budget - what counts as an acceptable level of SLO/SLIs not being met.

In a chat with all the stakeholders, start asking questions. Limit scope to something (app, CI/CD, test suite) - make sure we know what everyone expects for the system.

E.g., Want Devs to stop sitting around waiting for builds to kick off (SLO). SLI that is all builds start in 30s. Error budget is that 5% can take longer.

How to pull in the metrics? Honeycomb, Datadog, Splunk, bunch of others. Buildkite had agent metrics, with open telemetry built in.

E.g. speeding up test suite - once you've defined problem and SLI, parallelise tests, negative matching by speed.

In out drama, we want to increase reliability of the test suite. We can access metrics for that easily enough. Once the error budget is depleted, we can start to do stuff. Work on the least reliable tests first, quarantine flaky tests, etc.

Error budgets are great, but can be a difficult concept. If you are to use them, you need (mostly) to ignore the problem when the error budget is not exceeded - then down tools and improve things once it is. This makes for happy, productive developers, because they have clear focus.

And of course, the budget should not be carved in stone, there will be unexpected dragons.
