# Managing monorepos better - Turbo, initial analysis

Source: [turbo.build/repo/docs](https://turbo.build/repo/docs)

## What does Turbo do?

Turbo will cache the results of `package.json` scripts (`build`, `lint`, etc.)., and use the cache instead of rerunning the command when the inputs are unchanged.

You can configure the conditions for determining whether the inputs have changed - by default, it will look for public environment variables and the entire content of the workspace the command is running from, but you can make it look at more or less.

The cache will only be local by default, but by using a provider like `Vercel` you can set up a remote cache that your build pipelines can look at too.

Important: Turbo does not cache installs. You'll need [Zero Installs](https://yarnpkg.com/features/zero-installs) if you want that (which I've had some issues with).

## Requirements

Haven't tested it yet, but Turbo _should_ work with any project set up with yarn/npm on any normal operating system.

As above, if you want to optimise your build pipelines as well you'll need a `Vercel` account or similar to handle remote cache.

## Potential issues

Turbo is incompatible with nested workspaces. These are a bit of a pain, so it's probably worth flattening your workspaces anyway.

## Potential benefits

Turbo's main benefit is to speed up commands that don't need to be run from scratch repeatedly. This should save time on local dev with your usual git hooks, and on your pipeline as well with remote cache.

If you've already got an optimised process for deciding whether to run commands at all (e.g. only rerun tests on changed packages) Turbo might not provide such a big benefit. However, it does look like Turbo's configuration for deciding whether to rerun commands is fairly refined.


## Appendix A: NX

NX seems to provide a very similar product, along with NX Cloud to allow remote caching. If one was to set up command caching, more investigation should be done into which of Turbo and NX is more suitable.
