## The role of automation in protecting customer satisfaction - Damon Edwards (@damonedwards), Senior Director of Product at PagerDuty

This is a bit less specific of a talk. It's about strategy and focus.

Damon has been in a couple of companies, done a bunch of talks, and done a podcast called DevOps cafe.

"Automate all the things". A nice goal, but time, resource and skill constraints limit how much we can automate. So how do we make things better in the keyboard-using-trenches, and at levels up the line.

Customers want they want, and they want it to perform flawlessly. Operational side, what we will focus on is that second part, making it performing as flawlessly as possible.

## State of DevOps

Product delivery can be broken into three spheres: Dev, Ops, and Customer Service.

It used to be common for Devs to not even know what the application deployment looked like - they just had a dodgy word document.

And the Ops had all the accountability, but none of the control.

The DevOps movement has broken down that wall, and also added SRE in as a bridge where the wall used to be.

Service Level Objectives and Error budgets are tools for shared responsibility. Figure out what level of downtime the customer will actually be okay with, and make that the benchmark (that's an SLO). And make sure if the SLOs aren't met, it's everyone's responsibility, and give consequences if it goes wrong. E.g., Google tells Devs the Ops will hand them back applications if they don't hit SLOs (though this doesn't often happen).

"Error budget" means: if we have far less errors than would be still okay, we can speed up development, and break things a little more.

We want to give Ops more time to improve things, by removing toil. Toil is:

- Manual,
- Repetitive,
- Automatable,
- Tactical,
- Devoid of enduring value,
- Grows linearly with scale.

Toil is stuff that should really be automated.

Engineering work should reduce toil. If it doesn't, eventually you'll hit bankruptcy, where everyone's effort is used on toil, and nobody has time to do the engineering work required to get out of the hole.

SREs should be reducing toil (and should be given time to reduce toil).

## Where to focus?

Two things are needed:

1. Improved ability to respond to issues
2. Reduce toil so more work capacity is created

Both of can be managed through self-service automation.

## Goals of self-service automation

Self-service automation should:

- Enable anyone to do what previously was left to subject matter experts.
- Lead to shorter incidents and fewer escalations, leaving more time for engineering work.
- Fully enable "you-build-it-you-run-it"; self-service automation should mean you can hand over operations without giving a bunch of shell scripts and access to customer data, etc.

The person who noticed an issue should be able to click a button and run health checks.

There's still a wall between customer service and DevOps. That needs to be fixed. Self-service automation should fix it.

## Questions self-service automation should answer

Customer service needs to know:

- "Is this really a system issue?"
- "Is it related to another system issue?"
- "How do I gather details to reproduce?"

Customer service should not be stuck in the catch-22 of "Don't escalate and I annoy the customer, escalate and I annoy DevOps".

Customer service is currently a thankless job full of toil, so skill continually walks out the door.

Self-service automation should, for customer service:

- Instantly validate an issue;
- Automatically capture environment data to enrich a case;
- Check the state of the account and system without escalating;
- Quickly enable a basic administrative level check.

Often we have lots of little bespoke tools we use at an individual level to automate things, but they aren't shared. Even if others can access your tools, they don't know how to use them, or they don't have the same access level as you to customer data, etc.

It's hard to cross that gap.

## How PagerDuty provides self-service automation

PagerDuty uses Runbook automation to make self service a reality.

They make it easy for people to leverage existing tools and languages (they don't force everyone to write python scripts: bash or ansible or whatever should be fine). There should be as little resistance as possible when turning your bespoke script into a button anyone can click.

Fine grained access control and logging is crucial, it makes compliance your friend. PagerDuty offers this.

PagerDuty knows about your infrastructure. Self-service needs to know the environment model so it can remote execute with the right variables.

Provide workflow, notifications, error handling as a service. This stuff is hard programming work, and should be at the configuration level in your self-service automation system, so Devs building a self-service automation service don't have to code it all - just select options.
