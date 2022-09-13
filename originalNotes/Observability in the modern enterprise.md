# Observability in the Modern Enterprise - Mary-Jane Goddard, Principal Technical Sales Leader at IBM, and Madura Eleperuma, Observability Technical Specialist of IBM

Mary-Jane is wearing a cape, as lady Insight. She's been involved in data for a while, and data is everything. She covers Data, AI and Automation. Madura Eleperuma works for her, and is having his performance review on stage (that was a joke). The focus for this talk is "instant insight".

## The Talk

Monitoring is telling you when something is wrong, observability enables you to understand why. You can only monitor a system that's observable.

Imagine trying to solve a crime without CCTV or social media. That's why we need observability.

In the modern era, applications are business. Latency and downtime have direct impact of customer satisfaction and conversion.

What you hate about being on a support desk is when it's slow. Everything you can do to catch and solve problems before anyone gets on the phone and starts screaming is amazing.

## From the developer perspective

- You want to know whether problem is in code or ops, so you aren't in the war room without reason;
- You need to know if an issue is a bug in released code or a performance anomaly;
- Why spend hours manually instrumenting the code?
- If the app is running slow, you want to pinpoint why so you can fix it easily.

## From the ops perspective

- You want to prove systems are innocent as quickly as possible;
- You want to know which dev to talk to quickly;
- You want to know where data has gone wrong.

## How to keep both happy: Automation

You want a single self updating agent with automatic and continuous discovery of workloads and instrumentation of them. Instana provides this.

Instana is AI which helps you do the instrumentation. It offers:

- Complete fidelity (100% traces)
- 1 second granular metrics
- Out of the box curated knowledge base of application health signatures
- Contextualised views
- Dynamic graph, live statemap of applications
- Out-of-the box curated dashboards
- Same data with different perspectives or views, context follows you (business application perspective).
- When doing this type of digging, UI needs to be super intuitive and friendly. Instana is super intuitive, and super quick to install (3 minutes)
- SLA/SLO budget analysis.
- 5Intelligent Actions

When there's too many alerts, how do you even start?

Instana groups alerts into incidents, laying out all the issues that lead to the thing that affected the customer.

Automatically too. And on pipelines and canary deploys. Intuitive troubleshooting UI too.

Integrates with other tools:

- OpenTelemetry
- Collaboration tools/chat ops
- Logging tools
- ITSM tools
- CI/CD pipelines

There have SDKs available to improve on the capabilities.

Summary: instana tries to make Dev lives easy by automating as much as possible.
