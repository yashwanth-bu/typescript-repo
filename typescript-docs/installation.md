
# TypeScript Installation

## 1. Create Project Root Directory

```cmd
mkdir typescript-repo
cd typescript-repo
```

## 2. Initialize Node.js Project

```cmd
npm init -y
```

Creates `package.json` to manage project information and dependencies.

## 3. Install TypeScript

```cmd
npm install typescript --save-dev
```

Installs TypeScript as a development dependency.

## 4. Verify Installation

```cmd
npx tsc --version
```

If successful, it displays the installed TypeScript version.

### Understanding `npx`

npx (Node Package Execute) is a command-line utility bundled with npm (version 5.2.0 and later) used to execute Node.js packages directly without installing them globally on your system.

How `npx` works:

1. It first looks inside your project's local `node_modules/.bin` directory to see if the command already exists.
2. When a dependency is installed, npm automatically registers its command-line interface (CLI) tools in the `node_modules/.bin` folder.
3. Using `npx`, you can run the dependency's command directly in your project.

In short: `npx` executes CLI tools and package binaries.

## 5. Create TypeScript Configuration

```cmd
npx tsc --init
```

Creates `tsconfig.json` to configure TypeScript compilation.

## Installation Completed

TypeScript is installed and ready to use in the project.

**Important:** Run these commands from the project root directory.
