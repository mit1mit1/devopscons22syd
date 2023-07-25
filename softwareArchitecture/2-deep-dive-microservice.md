# Microservice Architecture

## Definitions

Everyone agrees that "microservice" is a broad term, and there's a fair bit of flexibility in what you mean by it. Here's a few definitions I thought were helpful - it should be some combination of these that we refer to from here on.

### Martin Fowler

Essentially, the big difference is team structure. Instead of teams of specialists, we have teams based on business capability. As the famous Amazon slogan says, "They build it, they ship it."

### microservices.io

Microservices - also known as the microservice architecture - is an architectural style that structures an application as a collection of services that are:

- Independently deployable
- Loosely coupled
- Organized around business capabilities
- Owned by a small team

## Benefits and Caveats

### 1. Cleaner Code is Promoted (but you can promote cleaner code without a network boundary)

There's less opportunity to write a big ball of spaghetti code when the codebase you're dealing with is smaller. There's also more chance to understand what you're working with from end to end, and write smarter code with that knowledge.

That said, you can get these same benefits from grouping the internals of a monolith into internal "services". They're still all part of the same codebase, are deployed together, and don't need a network to communicate with each other - but you can touch them in isolation from each other.

### 2. It's Easier (except for dealing with distributed transactions)

Each little box is simpler than a monolith, especially a badly organised monolith. But the boxes have to talk to each other, and that adds complexity. Be aware of this and be ready to deal with it.

### 3. It's Faster (except for the network calls)

Similarly, microservices are easier to optimise by nature of their individual simplicity - but because you now have network calls between layers, you've got a guaranteed I/O adding to time cost.

### 4. It's Simpler as an Engineer (but who owns the leftover stuff?)

"You build it, you ship it" is good for giving each team a clear set of things they are responsible for - but as an organisation, you need to put in work to make sure:
- You don't re-invent the wheel over and over (what can be shared between teams is);
- You don't kick cans down the road indefinitely (problems aren't ignored just because they don't neatly fit into a particular team's domain).

### 5. It's Easier to Scale (but you _can_ scale monoliths too with good organisation)

Because microservices are so neatly split up, you can load scale each microservice independently, which is a nice way to make sure you can cope with varying amounts of traffic efficiently.

But it's worth remembering you can do the same with a monolith if you break it into clusters which can scale independently.

## Challenges

As per the above caveats, sometimes microservices are not the right solution. The right solution is almost certainly _modular_, but a modular monolith may sometimes be more efficient than modular microservices.

However, even when the right solution is a microservice, there are some challenges that can come up:

### Refactoring Modularity

Because microservices break modules apart with "hard boundaries", it's difficult to refactor past those boundaries. It's difficult to get the right divisions into modules right at the start anyway - this is confounded by the difficulty in moving functionality from one microservice to another.

### Service Granularity

It's also hard to decide how "large" a microservice should be. In particular, there's not a clear cut answer to whether microservices can/should include multiple 'layers' (e.g. should microservices include both UI and backend, or should they split the two? Does it even count as microservices if you include both?).

### Front-end Modularization

Is still in it's infancy, and without front-end modularity we don't get the full range of benefits of microservices. You often don't want to put up with a monolith anywhere, including on the frontend.

### Resource Monitoring and Management

Microservice architecture multiplies the number of separate resources operating 'independently', and so multiplies the number we need to monitor and manage. For efficiency, you need to figure out how to scale monitoring and management of resources which are created and controlled independently.

### Failure Recovery

Because microservices are distributed, independent failures of services needs to be handled - this adds complexity, and is also a problem in it's infancy.

### Organizational Coordination

Because microservices put a lot of architectural responsibility and power on individual teams, there's a lot of possibility to re-invent the wheel over and over again. This is an inefficient use of time and also causes difficulty when teams need to work together, exchange members, etc. Organisations need to provide shared tools and practices to prevent this.

## Examples

If you google "examples of microservices", you mostly get a bunch of Medium blog posts about how Netflix or Amazon accelerate and scale by splitting into small teams - which is all well and good, but isn't very fleshed out.

So for more detail let's have a quick look at a couple of examples from our own projects: [real microservice examples](../personalNotes/real-microservices.md)

## References

- https://martinfowler.com/articles/microservices.html
- https://martinfowler.com/articles/microservice-trade-offs.html
- https://www.simform.com/blog/microservices-examples/
- https://microservices.io/patterns/microservices.html
- https://github.com/mfornos/awesome-microservices#articles--papers
- https://riak.com/posts/technical/microservices-please-dont/
- https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8354433
