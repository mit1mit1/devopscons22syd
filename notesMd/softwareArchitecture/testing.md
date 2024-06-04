## Testing pyramid, trophy etc.

Look at Testing Library and Kent C. Dodd's philosophy for frontend testing.

## Flaky tests

Occasionally tests will either be created that are flaky, or regress to a flaky state (when they fail a non-negligible percentage of the time, but pass if retried enough).

Martin Fowler has an article about flaky tests here: https://martinfowler.com/articles/nonDeterminism.html

The main problems with flaky tests are:
- Flaky tests make your test pipeline less useful - red builds no longer indicate a bug, they might just be the test randomly deciding not to work;
- As a corollary, flaky tests waste a bunch of time, effort, and build compute costs, as you just retry more and more to get them green;


I recommend this process to deal with flaky tests:

- As soon as a test is identified as flaky (and is in the main branch) quarantine it so it no longer runs on the main pipeline.
  - For a jest/vitest suite this means adding `skip` to the test block.
- At the same time, raise a bug item to fix, replace, or remove the test. Triage and discuss this item with the team.
  - If the team decides this is a high priority test, expediate the bug item and get it fixed.
  - If it is a low priority test but still worth having, put the item in the backlog.
  - If the test isn't worth keeping, just delete the test whenever is convenient.

If the team finds they are building up a backlog of skipped tests, reassess this strategy.