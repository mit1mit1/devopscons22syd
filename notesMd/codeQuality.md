# Code Quality

Or, how to make your code stink less.

## Patterns

### Helper functions

**Motivation:**

- [Long functions](https://refactoring.guru/smells/long-method) (>10 lines or so) are hard to understand, even if they have [comments](https://refactoring.guru/smells/comments);
- [Duplicate code](https://refactoring.guru/smells/duplicate-code) scattered throughout the codebase can be hard to maintain:
  - Note: some duplication is okay! It comes down to how confident you are that both places the code is used will _still_ need the same functionality in the future.
- Helper functions are easier to test than components when you have well-defined complex business logic:
  - E.g. if you are building a finance app and have some complex math in the frontend, it's worth extracting that and testing it independently of the UI.

**Approach:**

- [Extract](https://refactoring.guru/extract-method) the duplicate/long code to a helper function.
  - If the function is shared between components, put it in global helper function file (e.g. `src/helpers.ts`);
  - If the function is only used by this component, put it in a local helper function file (e.g. `src/components/ComponentName.helpers.ts`);
- It's [a good idea](https://www.dhiwise.com/post/a-guide-to-leveraging-react-helper-functions-for-development) to make the function you have extracted [functional](https://www.turing.com/kb/introduction-to-functional-programming) to a large extent:
  - Give it a single responsibility;
  - Don't let it mutate the inputs; don't let it have side effects;
  - Compose your helper functions from other helper functions to keep them small and single purpose;
- Give a descriptive name;

## Resources

### [Refactoring Guru](https://refactoring.guru/)

- A thorough collection of 'code smells' and suggestions for how to fix them.
- A bit focussed on backend-y code, and very Object-Oriented, but still has some useful ideas that are applicable more broadly.
