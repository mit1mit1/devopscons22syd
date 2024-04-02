# Optimising JavaScript Tests

## Identifying slow tests

- Locally, [Jest](https://jestjs.io/docs/cli#--verbose) and [Vitest](https://vitest.dev/config/#slowtestthreshold) can both be configured to output time taken for slow tests;
- In CI, [Buildkite](https://buildkite.com/docs/test-analytics/javascript-collectors) can be set up collect test analytics.

## Profiling slow tests

To figure out what bits in your tests are taking the longest you'll want to use a profiler. This can be done using the node ``--inspect-brk` inspector (see https://jestjs.io/docs/troubleshooting for an example of setting up the inspector for Jest).

Kent Dodds has a video about this step: [Profiling a jest test with the Chrome DevTools performance profiler](https://www.youtube.com/watch?v=RB2g-o39upo&t=2s)

## Resolving slow tests

To cut the bloat:

- Remove IO operations (`LocalStorage`, `console`, etc.);
- Make sure you aren't (waiting for timers)[https://jestjs.io/docs/timer-mocks];
- Mock/stub heavy dependencies;
- Tidy up `await` and `waitFor`;
- Make sure you're not making any unmocked network calls (use (jest-offline)[https://www.npmjs.com/package/jest-offline] to check);
- Remove tests entirely if you don't need them;

## General improvements

While you're at it, you might as well tidy up the (rest of the stuff)[https://kentcdodds.com/blog/common-mistakes-with-react-testing-library] Kent wants you to get rid of.
