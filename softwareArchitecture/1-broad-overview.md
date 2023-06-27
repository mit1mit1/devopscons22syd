# Software Architecture: A Broad Overview

## Intro

Before diving into the nitty gritty of a topic, I like to do a breadth-first analysis (otherwise you can get into scenarios like https://xkcd.com/761/).

Essentially all I will be doing at this stage is making a bunch of semi-informed Google searches, as well as looking at recommended reading from relevant uni courses, and summarising the stuff I find.

## What is Software Architecture?

### Definitions

There's quite a few ways of defining "Software Architecture":

1. “Architecture is about the important stuff. Whatever that is” (Ralph Johnson).

I.e., figure out what is important for your software, and spend effort designing this in a way that works well.

2. "Architecture is the decisions you wish you could get right early in a project" (Martin Fowler, referencing Ralph Johnson).

This definition adds a distinction - if something is going to get a lot harder to change once you've started writing code, then it should be considered "architecture". This corresponds with our intuition that architecture comes before construction.

3. "The software architecture of a system represents the design decisions related to overall system structure and behavior." (Software Engineering Institute, CMU)

That is, software architecture is how your system is designed at a high level. But, how high of a level?

### Distinctions

1. "Enterprise" vs. "Application"

Martin Fowler makes this distinction.

"Application Architecture" is the important decisions you make about:

- Code that developers see as a unit;
- Functionality that customers see as a unit;
- An initiative that is a distinct part of a budget.

"Enterprise Architecture" is the important decisions you make to coordinate teams that have a lot of distinct codebases and a lot of distinct users.

2. "Architecture" vs. "Architecture Patterns"

This isn't something I've seen anyone explicitly distinguish, but it is a distinction I personally will use from here on.

"Software Architecture" can apply to the actual design of a particular piece of software.

"Architecture Patterns" are copy-paste-able, well, patterns you can use. E.g. microservice architecture, BFF pattern, monolithic architecture.


### Next Steps

Dig into a particular pattern and it's usage. E.g. BFF pattern.

## References

_Overviews_

- https://en.wikipedia.org/wiki/Software_architecture
- https://martinfowler.com/architecture/
- https://www.freecodecamp.org/news/an-introduction-to-software-architecture-patterns/
- https://www.sei.cmu.edu/our-work/software-architecture/

_Lists of Architectural Patterns_

- https://towardsdatascience.com/10-common-software-architectural-patterns-in-a-nutshell-a0b47a1e9013
- https://www.redhat.com/architect/14-software-architecture-patterns

_Academic Papers_

- Cleland-Huang, J., Czauderna, A., & Keenan, E. (2013). A Persona-Based Approach for Exploring Architecturally Significant Requirements in Agile Projects. Lecture Notes in Computer Science, 18–33. doi:10.1007/978-3-642-37422-7_2
- Hachem, J. E., Pang, Z. Y., Chiprianov, V., Babar, A., & Aniorte, P. (2016). Model Driven Software Security Architecture of Systems-of-Systems. 2016 23rd Asia-Pacific Software Engineering Conference (APSEC). doi:10.1109/apsec.2016.023 