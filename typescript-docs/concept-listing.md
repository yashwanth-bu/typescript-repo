# TypeScript Concepts

## 1. Core TypeScript Concepts

| No. | Concept                       | Simple Explanation                                                                   |
| --: | ----------------------------- | ------------------------------------------------------------------------------------ |
|   1 | Type Annotations              | Specify the type of a variable, parameter, or return value.                          |
|   2 | Type Inference                | TypeScript automatically figures out a value's type.                                 |
|   3 | Union Types                   | Allow a value to have multiple possible types, like `string \| number`.             |
|   4 | Type Aliases                  | Create a reusable name for a type using `type`.                                    |
|   5 | Interfaces                    | Define the structure of an object.                                                   |
|   6 | Literal Types                 | Restrict a value to specific options, like `"success" \| "error"`.                  |
|   7 | Type Narrowing                | Use checks to find the exact type of a value.                                        |
|   8 | Optional Properties           | Make object properties optional using `?`.                                         |
|   9 | Generics                      | Write reusable code that works with different types.                                 |
|  10 | Enums                         | Define a set of named constant values.                                               |
|  11 | Tuples                        | Define arrays with a fixed structure and specific types at each position.            |
|  12 | Type Assertions               | Tell TypeScript what type you believe a value has.                                   |
|  13 | `unknown` vs `any`        | Understand safe and unsafe ways to work with values of uncertain types.              |
|  14 | `never` Type                | Represent values that never occur, such as a function that always throws an error.   |
|  15 | Utility Types                 | Transform existing types using tools like `Partial`, `Pick`, and `Omit`.       |
|  16 | `keyof` and `typeof`      | Get keys from a type and types from existing values.                                 |
|  17 | Type Guards                   | Check types safely using tools like `typeof`, `in`, and custom functions.        |
|  18 | Discriminated Unions          | Model different object shapes using a shared property that identifies each type.     |
|  19 | Function Overloads            | Define multiple valid ways to call the same function.                                |
|  20 | Declaration Files (`.d.ts`) | Describe types for JavaScript libraries without implementing their runtime behavior. |

## 2. Advanced TypeScript Topics

| No. | Concept                       | Simple Explanation                                                                                              |
| --: | ----------------------------- | --------------------------------------------------------------------------------------------------------------- |
|  21 | Advanced Generics             | Learn generic constraints, `extends`, `infer`, and conditional types.                                       |
|  22 | Advanced Type Manipulation    | Use mapped types, template literal types, and indexed access types to create and transform complex types.       |
|  23 | Classes and OOP               | Learn access modifiers, abstract classes, inheritance, and interfaces.                                          |
|  24 | Modules and Project Structure | Use imports, exports, path aliases, and organize large projects.                                                |
|  25 | Strict Type Safety            | Use strict mode, handle `null` safely, and avoid unsafe types such as `any`.                                |
|  26 | Async TypeScript              | Type promises, API responses, and asynchronous functions.                                                       |
|  27 | Runtime Validation            | Validate external data using libraries such as Zod because TypeScript types alone do not validate runtime data. |
|  28 | Type-Safe API Development     | Type requests, responses, errors, and shared types between frontend and backend.                                |
|  29 | Testing TypeScript            | Learn unit testing, mocking, and testing asynchronous code.                                                     |
|  30 | Design Patterns               | Apply dependency injection, the repository pattern, and service layers to build maintainable applications.      |

## 3. Additional Advanced TypeScript Concepts

| No. | Concept                    | Simple Explanation                                                                                  |
| --- | -------------------------- | --------------------------------------------------------------------------------------------------- |
| 31  | Conditional Types          | Choose a type based on a condition using `T extends U ? X : Y`.                                     |
| 32  | Mapped Types               | Create new types by transforming the properties of an existing type.                                |
| 33  | Template Literal Types     | Build string types using template literal syntax.                                                   |
| 34  | Indexed Access Types       | Access the type of a specific property using `T[K]`.                                                |
| 35  | Recursive Types            | Define types that refer to themselves, such as nested objects or trees.                             |
| 36  | Type Predicates            | Create custom type-checking functions using `parameter is Type`.                                    |
| 37  | Assertion Functions        | Assert that a condition is true and narrow types using `asserts`.                                   |
| 38  | Variance                   | Understand how type compatibility works for generic types, including covariance and contravariance. |
| 39  | Generic Defaults           | Provide default types for generic parameters.                                                       |
| 40  | `const` Assertions         | Preserve literal types and make object properties and arrays readonly using `as const`.             |
| 41  | `satisfies` Operator       | Check that a value matches a type without losing its more specific inferred type.                   |
| 42  | `readonly` Properties      | Prevent properties or array elements from being reassigned through a particular reference.          |
| 43  | Function Types             | Define the parameter and return types of functions.                                                 |
| 44  | Call Signatures            | Describe callable objects that may also have properties.                                            |
| 45  | Constructor Types          | Define the types of constructors and class constructors.                                            |
| 46  | Rest Parameters and Tuples | Type functions that accept a variable number of arguments.                                          |
| 47  | Declaration Merging        | Combine compatible declarations with the same name.                                                 |
| 48  | Module Augmentation        | Extend existing module declarations with additional type information.                               |
| 49  | Ambient Declarations       | Describe existing JavaScript variables, functions, or modules using `declare`.                      |
| 50  | Namespaces                 | Organize related declarations under a shared name, mainly in legacy or specialized codebases.       |

## 4. TypeScript Compiler and Configuration

| No. | Concept                      | Simple Explanation                                                                      |
| --- | ---------------------------- | --------------------------------------------------------------------------------------- |
| 51  | `tsconfig.json`              | Configure TypeScript compiler options and project behavior.                             |
| 52  | Compiler Options             | Control compilation, module output, strictness, and other TypeScript settings.          |
| 53  | Type Checking vs Compilation | Understand the difference between static type checking and generating JavaScript.       |
| 54  | Type Erasure                 | Understand why TypeScript types and interfaces do not exist at runtime.                 |
| 55  | Project References           | Split large TypeScript codebases into smaller, connected projects.                      |
| 56  | Build Modes                  | Use options such as `tsc --build` to build projects and their dependencies efficiently. |
| 57  | Module Resolution            | Understand how TypeScript locates imported files and packages.                          |
| 58  | Declaration Generation       | Generate `.d.ts` files using compiler options such as `declaration`.                    |
| 59  | Source Maps                  | Connect generated JavaScript back to the original TypeScript for debugging.             |
| 60  | Type Checking JavaScript     | Check JavaScript files using options such as `allowJs` and `checkJs`.                   |

## 5. Practical TypeScript and Real-World Development

| No. | Concept                         | Simple Explanation                                                                                             |
| --- | ------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| 61  | Error Handling                  | Handle errors safely using `try...catch`, typed results, and runtime checks.                                   |
| 62  | Type-Safe Error Types           | Represent expected failures using unions, discriminated unions, or result types.                               |
| 63  | Type-Safe Environment Variables | Validate and type configuration values loaded from environment variables.                                      |
| 64  | Type-Safe Event Handling        | Type DOM events, event handlers, and custom application events.                                                |
| 65  | DOM Manipulation                | Work with browser elements, event listeners, and DOM APIs using TypeScript types.                              |
| 66  | Type-Safe Forms                 | Type form values, validation errors, and submission handlers.                                                  |
| 67  | Type-Safe State Management      | Define and maintain reliable application state in frontend applications.                                       |
| 68  | Type-Safe Database Access       | Type database models, query results, and data operations.                                                      |
| 69  | Schema-First Type Design        | Generate or infer types from schemas using tools such as Zod.                                                  |
| 70  | Type-Safe Serialization         | Handle conversion between JavaScript values and formats such as JSON while accounting for runtime limitations. |
| 71  | Third-Party Type Definitions    | Use, install, and troubleshoot external library types, including `@types` packages.                            |
| 72  | Type Testing                    | Verify that types behave as intended using tools such as `tsd` or `expect-type`.                               |
| 73  | Type-Level Programming          | Use TypeScript's type system to perform complex transformations at compile time.                               |
| 74  | Performance of Type Checking    | Design types and project configurations to keep type checking efficient.                                       |
| 75  | Backward-Compatible API Types   | Evolve public types and interfaces without unnecessarily breaking existing consumers.                          |

# TypeScript Complete Learning Roadmap

| Stage | Concept Numbers | Learning Area | Topics Covered |
|---|---|---|---|
| Stage 1 | 1–8 | TypeScript Fundamentals | Type Annotations, Type Inference, Union Types, Type Aliases, Interfaces, Literal Types, Type Narrowing, Optional Properties |
| Stage 2 | 9–18 | Core Type System | Generics, Enums, Tuples, Type Assertions, `unknown` vs `any`, `never` Type, Utility Types, `keyof` and `typeof`, Type Guards, Discriminated Unions |
| Stage 3 | 19–20 | Functions and Declarations | Function Overloads, Declaration Files (`.d.ts`) |
| Stage 4 | 21–30 | Advanced TypeScript | Advanced Generics, Advanced Type Manipulation, Classes and OOP, Modules and Project Structure, Strict Type Safety, Async TypeScript, Runtime Validation, Type-Safe API Development, Testing TypeScript, Design Patterns |
| Stage 5 | 31–42 | Advanced Type System | Conditional Types, Mapped Types, Template Literal Types, Indexed Access Types, Recursive Types, Type Predicates, Assertion Functions, Variance, Generic Defaults, `const` Assertions, `satisfies` Operator, `readonly` Properties |
| Stage 6 | 43–50 | Functions and Declarations | Function Types, Call Signatures, Constructor Types, Rest Parameters and Tuples, Declaration Merging, Module Augmentation, Ambient Declarations, Namespaces |
| Stage 7 | 51–60 | Compiler and Tooling | `tsconfig.json`, Compiler Options, Type Checking vs Compilation, Type Erasure, Project References, Build Modes, Module Resolution, Declaration Generation, Source Maps, Type Checking JavaScript |
| Stage 8 | 61–75 | Production Development | Error Handling, Type-Safe Error Types, Type-Safe Environment Variables, Type-Safe Event Handling, DOM Manipulation, Type-Safe Forms, Type-Safe State Management, Type-Safe Database Access, Schema-First Type Design, Type-Safe Serialization, Third-Party Type Definitions, Type Testing, Type-Level Programming, Performance of Type Checking, Backward-Compatible API Types |

## Important Note

Some concepts overlap between the original 30 topics and the additional advanced topics. For example, conditional types, mapped types, and template literal types are introduced under Advanced Type Manipulation and then explored individually.

The roadmap retains these overlaps intentionally to support progressive learning, moving from fundamentals to advanced type-system concepts, compiler tooling, and production development.