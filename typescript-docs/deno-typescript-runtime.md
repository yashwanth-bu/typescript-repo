# Deno: TypeScript Runtime

## 1. What is Deno?

Deno is a runtime for JavaScript, TypeScript, and WebAssembly. Like Node.js, it lets you run JavaScript outside a web browser.

Deno includes tools for running code, type-checking TypeScript, formatting, linting, and testing. It is built on the V8 JavaScript engine and uses Rust for parts of its implementation.

## 2. How does Deno work?

1. Write code in a file such as `index.ts`.
2. Run it with Deno:

   ```bash
   deno run index.ts
   ```

3. Deno handles TypeScript support and executes the program. You do not need to manually compile the file into a `.js` file first.

Example `index.ts`:

```typescript
const message: string = "Hello from Deno!";
console.log(message);
```

Run it:

```bash
deno run index.ts
```

### Type-checking

Deno type-checks TypeScript by default when using `deno run`, unless type-checking is disabled through a flag or configuration. You can explicitly check a file without executing it:

```bash
deno check index.ts
```

Example of a type error:

```typescript
const age: number = "twenty";
console.log(age);
```

Deno should report that the string value is not assignable to `number`. Fix it by assigning a number:

```typescript
const age: number = 20;
console.log(age);
```

Type-checking is static, not runtime validation of external data. Type annotations do not automatically validate JSON, API responses, or user input.

## 3. Deno vs Node.js vs TSX

| Feature | Deno | Node.js | TSX |
|---|---|---|---|
| What it is | JavaScript/TypeScript runtime | JavaScript runtime | TypeScript/JSX execution tool used with Node.js |
| Runs TypeScript directly | Yes | Supported in recent versions, with restrictions depending on version and features | Yes |
| Type-checks by default | Usually yes for `deno run` | No | No |
| Explicit type-check command | `deno check file.ts` | Use `tsc --noEmit` | Use `tsc --noEmit` |
| Requires manually creating `.js` output | No | No for supported direct execution | No |
| npm package support | Yes, with Deno's package compatibility | Native ecosystem | Uses Node.js package ecosystem |
| Best fit | Integrated runtime and developer tools | Common choice for production server-side JavaScript and TypeScript projects | Convenient TypeScript execution within a Node.js project |

**Key distinction:** `tsx` runs TypeScript but does not type-check it by itself. To type-check a Node.js project, run `tsc --noEmit` before `tsx`. Deno combines more of this workflow into its runtime and tooling.

## 4. Install Deno on Windows

Open PowerShell and run the official installer:

```powershell
irm https://deno.land/install.ps1 | iex
```

Close and reopen your terminal, then verify the installation:

```powershell
deno --version
```

If the command is not recognized, confirm that Deno's install directory is on your `PATH`, then restart the terminal.

## 5. Install Deno on macOS or Linux

Use the official install script:

```bash
curl -fsSL https://deno.land/install.sh | sh
```

Restart the terminal if necessary, then verify:

```bash
deno --version
```

For other installation methods and the latest instructions, see the official documentation: https://docs.deno.com/runtime/getting_started/installation/

## 6. Useful commands

| Command | What it does |
|---|---|
| `deno run index.ts` | Type-checks (by default) and runs the file |
| `deno check index.ts` | Type-checks without running the file |
| `deno fmt` | Formats supported project files |
| `deno lint` | Runs Deno's linter |
| `deno test` | Runs tests discovered by Deno |
| `deno --version` | Shows the installed version |

## 7. Permissions

Deno uses a permission system for access to resources such as the network, files, and environment variables. A script may need explicit permission flags, for example:

```bash
deno run --allow-read index.ts
```

Grant only the permissions the program needs. Do not add broad permissions without understanding why they are required.

## Summary

Deno lets you run TypeScript directly and provides integrated developer tools. Start with `deno run index.ts`; use `deno check index.ts` when you want a type-check without executing the program. If your project specifically targets Node.js, using Node.js with `tsc` and `tsx` may fit its ecosystem better.
