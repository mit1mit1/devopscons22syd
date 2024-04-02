# Microfrontend Architecture

## Definitions

You may be thinking, "Microservice", "Microfrontend" - potato potato? And you'd be right (sort-of).

The concept of latter emerged in the wake of former. Microservices were gaining popularity, companies were splitting their backends into team-managed bite-size chunks - but often the UI got left as a huge monolith.

To deal with this, teams started simply applying the same principles to the frontend. Break it into a collection of frontends that are:

- Independently deployable
- Loosely coupled
- Organized around business capabilities
- Owned by a small team

## Approaches

The web comes with a set of restraints. We need to somehow build and deploy separate codebases, that end up turning into HTML, JS and CSS that are all displayed on the same page - and we need the styles and functions not to clash with each other. We can split the ways of doing this into a fairly tight set of possibilities.

### Server Side Composition

In this approach, each team generates and deploys a HTML fragment/s. The parent app then sticks the fragments together (presumably using a templating engine of some sort), and serves the complete page.

As long as teams can independently develop and deploy their fragments, this gives some of the benefits of microfrontends.

It's an old tech, but it checks out. You might run into some trickiness making styling independent, and it may not be appropriate if you want to re-use your microfrontends.

### Build-time Dependencies

Here each team publishes a package (e.g. NPM package) containing their microfrontend. The parent app consumes them as dependencies and renders them however it wants to.

The trouble here is that to release anything to clients, you need to bump the version in the parent app - locking the release process together. This slows down the release enough that it's un-endorsed by Martin Fowler's blog.

### IFrames

Another known and old solution is the humble iframe. Teams each deploy pages independently, and the parent app consumes each page in an iframe.

This works reasonably well if you can cope with having very hard barriers between your microfrontends. It can cause pain if you want them to interact well, and can also have (standard iframe) issues with responsiveness and history.

### Run-time Dependencies

Finally, each team can publish a JS package and expose it on a public facing URL (typically on a CDN). The parent app then consumes these as scripts, and lets them do their work.

This gives good flexibility if you need your microfrontends to interact with each other, and maximum speed and decoupling of releases. Of course, that flexibility must come with caution - you'll need to make sure your releases are compatible, etc.

A common way to include these packages in a nicely isolated way is for each microfrontend to publish a package that defines a `web-component`, with all their functionality contained inside that. This lets you hook into the web-component spec to pass data around, which might feel more natural, and also lets you use the `shadow dom` (dun-dun-dahhhhh).

## Common Challenges

### Styling

Mounting a bunch of CSS written by different teams to the same page could cause conflicts (assuming you aren't going with iframes). To avoid conflicts:

- Use a class naming convention, e.g. https://getbem.com/;
- Use SASS to namespace classes;
- Use CSS-in-JS to apply styles through uniquely generated classes;
- Use web components and a shadow DOM to isolate the CSS entirely;

### Keeping it DRY

There's a high likelihood your independent microfrontends are still going to want to do similar things. You don't want to repeat effort, and you do want to make sure the end user gets a consistent experience.

The main way to deal with this is to create a shared UI component library. Recommendations when doing so:
- Keep it dumb and generic;
- Make sure there is a clear process for ownership so it doesn't get neglected or turn into a mess - make sure there is an easy contribution process;
- Make it isn't developed in isolation for how it is used, so it is actually useful.

### Interactions between frontends

You don't want to couple your frontends together any more than you can avoid. Some nice ways to let them interact when necessary include:

- Push custom events in one and listen for them in another;
- Pass callbacks as props;
- Change and listen to the URL from the microfrontends;

### Testing

While the testing pyramid implies most automated tests shouldn't need you to integrate the frontends together, the tip of the pyramid will require you to test the microfrontends working together. A few tools that are good for this level are Cypress, Selenium and Playwright. Contract testing between the microfrontends might fit well as a slice below the tip of the pyramid.

### Hooking it into the backends

Ideally each team owns their own backend service. If a BFF helps keep these independent, go for it (the original idea behind BFFs was to keep web/mobile/etc. logic separate, but they work for this too). However, if a microfrontend is just talking to an existing stable and/or independent API, there's probably not much point to a BFF.

## References

- [Martin Fowler on Microfrontends](https://martinfowler.com/articles/micro-frontends.html)
- [microfrontends.org](https://micro-frontends.org/)
- [Awesome Microfrontends by Christian Ulbrich](https://github.com/ChristianUlbrich/awesome-microfrontends)
- [Elisabeth Engel on Microfrontends](https://micro-frontends.zeef.com/elisabeth.engel?ref=elisabeth.engel&share=ee53d51a914b4951ae5c94ece97642fc)
- [A software architect's approach towards microfrontends](https://www.angulararchitects.io/aktuelles/a-software-architects-approach-towards/)
- [OTS Microservices Docker Journal](https://www.sigs-datacom.de/uploads/tx_dmjournals/attermeyer_OTS_Microservices_Docker_16.pdf?utm_medium=referral&utm_campaign=ZEEF&utm_source=https%3A%2F%2Fmicro-frontends.zeef.com%2Felisabeth.engel) (Deutsch)

