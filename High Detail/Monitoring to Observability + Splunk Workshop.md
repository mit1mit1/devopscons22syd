# Monitoring to Observability: Empowering DevOps and Digital Business - Koray Harman, DevOps Specialist of Splunk

(Missed first 5-10 minutes)

## What is observability

We have a closed pizza oven, find it burns pizzas - what do we do? Add temperature gauges, maybe a window. We start to discover our unknown unknowns; e.g. we didn't know it was possible for the different burners to burn at different temperatures, but one is constantly twice the heat of the others.

O11y == observability. It gives us better customer experience, optimised cost, accelerated time for delivery.

Every company is on a different modernisation stage, with products at different levels of modernisation. Thus, taking on new bells and whistles adds complexity - we need to make sure it is kept in check, make sure we know what the new bells and whistles are actually doing.

## Three pillars of observability (which must be kept very tightly connected)

Observability should consist of:

- Metrics - a snapshot in time value of what is happening
- Traces - telling us where it is happening
- Logs - telling us the root cause issue

## Supporting tenets of observability

Observability should be:

- Full stack and e2e, got to know data across all layers of the stack (full fidelity, capture 100% of telemetry data across all layers of the stack)

- Real time, with seconds delay, not minutes

- Analytics-powered: we can't work with 4 million traces without analytics - but each business knows their own business logic, so the platform needs to let them ask open enough questions

- Scaleable to enterprise grade - massively scalable, with teams and permissions. Needs to be fully programmable, UI config isn't feasible - 'monitoring as code' is a must

- Open standards so we aren't locked into a particular vendor (see Open Telemetry)

Splunk specifies APIs, SDKs, Data so that you don't have to dig into how your particular OS plays with logs.

It has an open telemetry collector, and language specific functions too.

## Performance matters

BBC found a 1s slower page load loses 10% of visitors. Walmart found similar, as did Vodaphone with largest contentful paint...

Observability should make things smoother for the Devs too.

Beyond performance, maturing observability should unlock business insights. It should show revenue growth per item of work, deeper understanding of cost per performance insights, cost of service APIs, pivot by customer, correlate UX with APIs, tell you which services are critical.

## Hit the ground running

Start early and mature together; retrofitting observability into an existing complex solution is harder than integration from the get go.

Embed observability into all stages of the DevOps loop.

Make sure you use open standards for data ingestion. You should be with a vendor because you want what they offer, not because you've got a billion dollars of tech debt baked in.

# Splunk Observability Workshop

Run by some observability and Sales Engineers who flew in from Melbourne.

## Intros

In a nutshell, Iress is currently using Amazon services, so we have Cloudwatch and CloudLogs. We want leading indicators.

## Skipping Through Observability

Every company is on a cloud journey, somewhere in the path from tightly coupled apps on premises, to lift and shift, to re-factor hybrid frontends, to Re-Architect, Cloud-Native.

The variety of services everything talks to adds complexity.

A potential customer talked to Splunk, said that "if there is an issue, and one of the two or three people who know what is going on aren't there, they're stuffed".

Brent Miller: "Observability is about getting answers to questions we didn't know we'd have to ask". Less of a tool and more of a mindset.

Open standards are crucial if you ever, for any reason, want to switch tools. If you want to swap from New Relic to Splunk, for example.

Why focus so much on Open Telemetry (OTEL)? It's big. Everyone claims support for it, fine print usually rules out bits of it. Splunk is the biggest contributor to it though - they're invested.

Observability is a data problem (see the three pillars in the above talk).

## The Data Foundation for the Hybrid World

Splunk-built Security and Observability.

Splunk platform: Streaming, Machine Learning, Scalable Index, Search and Visualization, Collaboration and Orchestration.

E.g. a car company uses Splunk to keep track of how their cars are working. A toll company compares cars coming through toll gates by whether they have tags.

You can Splunk the data coming back from a boat. Any industry with any kind of performance data coming back can use Splunk.

Specifically looking at the observability cloud, there are six products.

- Application Performance Monitoring
- Synthetics: Uptime checks, deployment checks, how would new version push affect prod deployment, ..
- Infrastructure monitoring: relies on metrics, integrable with AWS, Azure, Google Cloud metrics, etc.. It can use the metrics RDS sends to CloudWatch. Can run queries and convert into metrics.
- Log Observers: for logging needs. Can run queries in a UI too.
- RUM.
- On-Call: this is the pager duty. Can integrate with PagerDuty too.

Individually a flavour of all these solutions exist from different vendors. The beauty of Splunk is combining all of these together .

E.g. You can start from RUM, find when a issue started - go to AMP find out what the problem is related to - hop over to infrastructure monitoring and find the board that is broken, go to log observer and find the related logs. On-call alerts you to this. This is what they mean by End to End Observability.

## Demo:

1. Go through https://signalfx.github.io/observability-workshop/latest/imt/

OTEL also means you can send data to multiple backends. (OTEL is actually kind of cool I think).

User access levels can be set so you can only show prod logs (or PII logs?) to some people, you can nuke stuff if PII sneaks through to AMP.

There's AI to help diagnose root cause!

https://dev.splunk.com/observability/docs/signalflow/methods

Monetary benefit for splunk core customers who are using the observability stuff too.

If people want to look into it from our company, options are:

1. Engineers can make a trial account.
2. If features are unavailable or you want to expand the trial talk to the people who ran the workshop (who are their technical customer facing team).

First, we need to better understand where our gaps are. We need to compare to Datadog RUM as well.
