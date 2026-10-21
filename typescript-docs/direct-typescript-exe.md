# Direct TypeScript Execution with `tsc` + `tsx`

This setup lets you run a TypeScript file with one command while checking TypeScript types before execution.

## What the tools do

- **`tsc`**: TypeScript's compiler and type checker. With `--noEmit`, it checks the code without writing JavaScript files.
- **`tsx`**: Executes TypeScript files without requiring you to manually compile them to `.js` first. By itself, it does **not** type-check the code.
- **Together**: `tsc` checks the project first. If checking succeeds, `tsx` runs the entry file.

## 1. Requirements

Install [Node.js](https://nodejs.org/) first. Then open a terminal in your project directory.

## 2. Initialize a project

If the project does not already have a `package.json`, run:

```bash
npm init -y
```

## 3. Install the tools

```bash
npm install -D typescript tsx
```

The `-D` flag saves both packages as development dependencies in `package.json`.

## 4. Configure TypeScript

Create `tsconfig.json` in the project root:

```json
{
  "compilerOptions": {
    "strict": true,
    "noEmit": true,
    "target": "ESNext",
    "module": "NodeNext",
    "moduleResolution": "NodeNext"
  },
  "include": ["**/*.ts"],
  "exclude": ["node_modules"]
}
```

Key options:

- **`strict: true`** enables TypeScript's strict type-checking options.
- **`noEmit: true`** prevents `tsc` from generating JavaScript output.
- **`module` and `moduleResolution`** configure Node.js-style module handling.
- **`include`** identifies TypeScript files for checking; adjust it if your source files live in a specific folder or you use other TypeScript file extensions.

## 5. Add a one-command script

In `package.json`, add or update the `scripts` section like this:

```json
{
  "scripts": {
    "dev": "tsc && tsx index.ts"
  }
}
```

If `package.json` already contains other fields or scripts, keep them and only add the `dev` entry.

## 6. Create and run a TypeScript file

Create `index.ts`:

```typescript
const message: string = "Hello from TypeScript!";
console.log(message);
```

Run the project with one command:

```bash
npm run dev
```

The command runs in this order:

1. `tsc` checks the files covered by `tsconfig.json`.
2. If type-checking fails, `&&` stops the command and `tsx` does not run.
3. If type-checking succeeds, `tsx index.ts` executes the entry file.
4. `tsx` does not create a compiled `index.js` file in your project.

## 7. Verify type-checking

Temporarily put this in `index.ts`:

```typescript
const age: number = "twenty";
console.log(age);
```

Run:

```bash
npm run dev
```

`tsc` should report a type error, and the program should not execute. Fix it by assigning a number:

```typescript
const age: number = 20;
console.log(age);
```

## Useful commands

| Command              | What it does                                                      |
| -------------------- | ----------------------------------------------------------------- |
| `npm run dev`      | Type-checks first, then runs `index.ts` if checking passes      |
| `npx tsc --noEmit` | Checks types without running the program or generating JavaScript |
| `npx tsx index.ts` | Runs the file directly, without a prior type-check                |

## Limitations to know

- Type-checking happens before execution; TypeScript types are not enforced at runtime.
- External data, such as API responses or parsed JSON, needs runtime validation if its shape must be trusted.
- Only files included by your TypeScript configuration are checked. Review `include`, `exclude`, and any project-specific settings.
- The command checks the code each time you run it; it does not continuously check after every edit.

## Summary

Use **`npm run dev`** as your one command. It runs strict TypeScript checks with `tsc`, then executes `index.ts` with `tsx` only if checking succeeds. No manual JavaScript compilation step is required.
