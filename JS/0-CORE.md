# JavaScript-Core

> [Next (Global Execution Context & Temporal Dead Zone)](./1-GEC-TDZ.md)

## Core Language

### JavaScript = ECMAScript + Web APIs + DOM

- JavaScript is not just one single specification—it is a combination of three main components:
  - **ECMAScript** – the core language features and syntax.
  - **Web APIs** – browser-provided features like `setTimeout`, `fetch`, `console`, etc.
  - **DOM (Document Object Model)** – an interface provided by the browser to interact with HTML and XML documents.

> 🧠 ECMAScript defines the _language_, while Web APIs and DOM define the _environment_ JavaScript runs in (usually the browser).

- **ECMA** stands for **European Computer Manufacturers Association**, the group behind the standardization of ECMAScript.

## ECMAScript

- **ECMAScript** is the official specification of the JavaScript language, maintained by a standards committee known as **TC39**.
- It defines the core features of the language that every JavaScript engine (like V8, SpiderMonkey) must follow.

### What Comes Under ECMAScript?

These are the building blocks of JavaScript as a language (excluding browser features):

#### ✅ Language Syntax

- Rules on how code should be written and structured.
- Includes:
  - Keywords (`if`, `for`, `function`, `return`, etc.)
  - Code structure rules (semicolons, brackets)
  - Literal values (`{}`, `[]`, `""`, etc.)
  - Variable declarations (`var`, `let`, `const`)

#### ✅ Error Handling

- Built-in mechanisms to handle errors:
  - `try...catch`
  - `throw` keyword
  - Creating and using custom errors

#### ✅ Data Types

- The types that can be stored and manipulated:
  - `boolean`
  - `number`
  - `string`
  - `null`
  - `undefined`
  - `object`
  - `symbol`
  - `function` (a special kind of object)

#### ✅ Inheritance via Prototypes

- JavaScript uses **prototype-based inheritance** instead of class-based inheritance (although `class` syntax exists, it's just syntactic sugar over prototypes).
- Every object in JS has an internal link to another object called its prototype.

#### ✅ Built-in Objects and Utility Functions

- ECMAScript includes several built-in global objects and methods such as:
  - `JSON`
  - `Math`
  - Array methods (`map`, `filter`, `reduce`, etc.)
  - `parseInt`, `parseFloat`
  - `encodeURI`, `decodeURI`

#### ✅ Strict Mode

- Introduced to catch common coding mistakes and unsafe actions.
- Activated by placing `"use strict";` at the top of your code.
- Examples:
  - Prevents use of undeclared variables
  - Makes assignment to read-only properties throw errors

#### ✅ Modules

- Supports modular programming using `import` and `export`.
- Helps in code separation and reusability.

#### ✅ Memory Model

- Specifies how variables and values are stored and accessed during program execution.
- Closely related to the concepts of:
  - **Execution Contexts** (like GEC)
  - **Hoisting**
  - **Scopes and Closures**

---

### Global Execution Context

- Everything defined under ECMAScript (functions, variables, objects, etc.) runs inside an **Execution Context**.
- When a script starts, the JavaScript engine creates the **Global Execution Context (GEC)** based on ECMAScript rules.
- The GEC is where:
  - The global object is created (`window` in browser, `global` in Node.js)
  - The `this` keyword is defined
  - All globally scoped variables and functions live
- ECMAScript governs **how** and **where** all this happens, making it the foundation of how JavaScript runs internally.

> Without ECMAScript, there would be no rules for how JavaScript behaves — it's the heart of the language.

### [Next (Global Execution Context & Temporal Dead Zone)](./1-GEC-TDZ.md)
