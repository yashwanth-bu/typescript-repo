# Global TypeScript Installation

## 1\. Install TypeScript Globally

```Shell
npm install -g typescript
```

Installs TypeScript globally on your system, allowing you to use the TypeScript compiler commands from any directory without installing TypeScript separately in every project.

**Understanding** **`-g`** **:**

- `-g` stands for global installation.
- The TypeScript compiler becomes available through the system's command line.
- You can use commands such as `tsc` from different project directories.
- Global installation does not automatically install TypeScript inside every project's `node_modules` directory.

## 2\. Verify Global Installation

```Shell
tsc --version
```

Displays the globally installed TypeScript version.

You can also check where the compiler command is located:

```Shell
where tsc
```

This command works on Windows Command Prompt and displays the location of the `tsc` executable.

**Note:** If `tsc` is not recognized, check whether Node.js and npm are installed and whether npm's global executable directory is included in your system's `PATH`.

## 3\. Create a TypeScript Project

```Shell
mkdir typescript-global-demo
cd typescript-global-demo
```

Create a TypeScript file named `app.ts` and add the following code:

```TypeScript
let message: string = "Hello, TypeScript!";
console.log(message);
```

This is a simple TypeScript program that declares a string variable and prints its value.

## 4\. Compile TypeScript into JavaScript

```Shell
tsc app.ts
```

Compiles `app.ts` into a JavaScript file named `app.js`.

The generated JavaScript file can be executed by Node.js.

**Important:** TypeScript does not normally execute `.ts` files directly through the traditional compiler workflow. The `tsc` command compiles TypeScript into JavaScript.

## 5\. Run the Generated JavaScript

```Shell
node app.js
```

Output:

```Shell
Hello, TypeScript!
```

Here, `tsc` compiles the TypeScript file, while `node` executes the resulting JavaScript file.

## 6\. Check TypeScript Without Generating JavaScript

```Shell
tsc --noEmit app.ts
```

Checks the TypeScript file for type errors without generating a JavaScript output file.

This is useful when you only want to validate the code.

## 7\. Initialize TypeScript Configuration

```Shell
tsc --init
```

Creates a `tsconfig.json` file in the current directory.

This file contains compiler configuration options, such as the JavaScript target version, module system, strict type-checking rules, and other compilation settings.

**Important:** Run this command inside your project directory to create a configuration file for that project.

## 8\. Compile Using `tsconfig.json`

When a project contains a `tsconfig.json` file, run:

```Shell
tsc
```

The compiler reads the configuration file and compiles the TypeScript files included in the project.

For example, if the project contains:

```
typescript-global-demo/
├── app.ts
├── math.ts
└── tsconfig.json
```

Running `tsc` uses the configuration and file-selection rules defined in `tsconfig.json`.

To compile automatically whenever a TypeScript file changes, use:

```Shell
tsc --watch
```

The compiler watches the project files and recompiles them when changes are detected.

## 9\. Understand How Global TypeScript Handles Multiple Projects

Suppose you have multiple projects on your system:

```
Projects/
├── project-one/
│   ├── app.ts
│   └── tsconfig.json
├── project-two/
│   ├── index.ts
│   └── tsconfig.json
└── project-three/
    ├── main.ts
    └── tsconfig.json
```

If TypeScript is installed globally, all three projects can use the `tsc` command without installing TypeScript locally in each project.

Navigate into a project and run:

```Shell
cd project-one
tsc
```

The compiler uses `project-one/tsconfig.json`.

Similarly:

```Shell
cd ../project-two
tsc
```

The compiler uses `project-two/tsconfig.json`.

Each project can have different compiler settings even though the same globally installed TypeScript compiler is used.

### How Does Configuration Work Across Projects?

Global TypeScript installation and TypeScript configuration serve different purposes:

- **Global TypeScript installation:** Makes the `tsc` command available system-wide.
- **`tsconfig.json`** **:** Defines how TypeScript should compile a particular project.
- **`package.json`** **:** Stores project metadata, scripts, and dependencies.
- **`node_modules`** **:** Stores packages installed locally for a project.

The global compiler does not create one shared `tsconfig.json` that automatically controls every project. By default, the compiler uses the configuration associated with the project you compile.

If a project has no `tsconfig.json`, you can compile an explicitly specified file:

```Shell
tsc app.ts
```

However, when you run `tsc` without specifying input files, the compiler searches for a `tsconfig.json` in the current directory. If none is found, it reports an error.

## 10\. Global Installation vs. Local Installation

| Feature                           | Global installation                     | Local installation                    |
| --------------------------------- | --------------------------------------- | ------------------------------------- |
| Command                           | `tsc`                                 | `npx tsc`                           |
| Installation                      | `npm install -g typescript`           | `npm install typescript --save-dev` |
| Compiler location                 | npm's global directory                  | Project's `node_modules`            |
| Available across projects         | Yes                                     | Primarily within the project          |
| Project-specific compiler version | Not guaranteed                          | Yes, when using the local version     |
| Best suited for                   | Learning and convenient system-wide use | Team projects and reproducible builds |

**Recommendation:** Global installation is convenient for learning TypeScript and running simple programs. For professional projects, local installation is generally preferred because each project can specify its TypeScript version in `package.json` and its lockfile.

## Installation Completed

TypeScript is globally installed and ready to use.

You can now use the following commands:

```Shell
tsc --version
tsc app.ts
node app.js
tsc --noEmit app.ts
tsc --init
tsc
tsc --watch
```

**Remember:** Global installation provides the compiler command across your system, while each project's `tsconfig.json` controls its own compilation settings. These are separate concepts.
