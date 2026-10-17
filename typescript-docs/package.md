#  Package Installations

## 1. TypeScript

**Purpose:** Compiles TypeScript into JavaScript.

```cmd
npm install typescript --save-dev
```

## 2. Node.js Types

**Package:** `@types/node`

**Purpose:** Provides TypeScript definitions for Node.js built-in modules such as `fs`, `path`, and `process`.

```cmd
npm install @types/node --save-dev
```

## 3. Express

**Purpose:** Creates web servers and REST APIs.

```cmd
npm install express
```

## 4. Express Types

**Package:** `@types/express`

**Purpose:** Provides TypeScript definitions for Express.

```cmd
npm install @types/express --save-dev
```

## 5. Development Tools

### tsx

**Purpose:** Runs TypeScript files directly during development.

```cmd
npm install tsx --save-dev
```

### nodemon

**Purpose:** Automatically restarts a Node.js application when files change.

```cmd
npm install nodemon --save-dev
```

## Important Notes

- `npm install package-name` installs a runtime dependency.
- `npm install package-name --save-dev` installs a development dependency.
- `@types/package-name` provides TypeScript type definitions for packages that need them.
- Run commands from the project root directory.

**Note:** You don't need every package in every project. Install only what your project uses.
