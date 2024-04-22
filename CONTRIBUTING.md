# CONTRIBUTING

### Prerequisites

- Install Node version 20 or higher from [nodejs.org](https://nodejs.org/en/download/)
- Install typescript: `npm -i typescript --save-dev`
- Install the linter: `npm -i gts --save-dev`

### Build instructions

Build the action with:

```
npm run compile
```

The compiler generates code that doesn't satisfy the linter, so it's usually a
good idea to run `npm run fix` after compiling.

Check for linter errors with: 

```
npm run lint
```
