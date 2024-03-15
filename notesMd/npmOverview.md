# NPM Overview

## Definitions

- A _package_ is a file or directory described by a _package.json_ file, or any repo, zip, URL, etc. that gives a file or directory described by a _package.json_.
- A _module_ is anything that can be loaded by using `require()` in a Node.js program, e.g.:
  - A folder with a `package.json` file containing a `main` field; or;
  - A folder with an `index.js` file in it; or;
  - A JavaScript file.

A _package_ may or may not be a _module_.

A _module_ may or may not be a _package_.

## References

Mostly taken from the [NPM docs](https://npm.github.io/how-npm-works-docs/).
