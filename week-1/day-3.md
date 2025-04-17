# Assignment 2 (Day 3): Creating and Using JavaScript Modules

## Objective

- Learn how to create reusable JavaScript modules in Node.js.
- Practice importing and exporting functions across multiple files.
- Build a simple Node.js application that demonstrates modular code organization.

## Instructions

Thought for a couple of seconds

### **Assignment — ES Modules Edition**

---

## Part 1 · Project Setup

1. **Create a project folder**

   ```bash
   mkdir js‑modules‑practice
   cd js‑modules‑practice
   ```

2. **Initialize NPM**

   ```bash
   npm init -y
   ```

3. **Enable ES modules**
   Add `"type": "module"` to the root of `package.json`:

- Example of where it could be placed in your package.json. (You only need one line out of this snippet, not every part of it.)

  ```jsonc
  {
    "name": "js-modules-practice",
    "type": "module",
    "version": "1.0.0"
  }
  ```

---

## Part 2 · Utility Modules

Create two files in the project root:

| File                 | Minimum requirement                                                    |
| -------------------- | ---------------------------------------------------------------------- |
| **`mathUtils.js`**   | Export at least two math functions using `export` syntax               |
| **`stringUtils.js`** | Export at least one string‑manipulation function using `export` syntax |



---

## Part 3 · Main Script

Create **`index.js`** that:

1. Imports the functions from both utility modules using ES `import` syntax.

2. Calls each function at least once and logs the results to the console.

Run with:

```bash
node index.js
```

---

## Part 4 · Conceptual Reflection

Use **`README.md`** (not a separate file) to answer **both** prompts in 1–3 concise sentences each:

1. **`export` / `import` vs `module.exports` / `require`**

   - Describe one key technical difference.

2. **Why choose ES modules for modern Node projects?**

   - State one clear reason.

---

## Submission

1. Push **all project files** (`package.json`, `mathUtils.js`, `stringUtils.js`, `index.js`, `README.md`) to a GitHub repo named **`js-modules-practice`**.

2. Share the repository link.

---

## Rubric · 25 pts

| #   | Criteria                        | Limited (0 pts)                 | Partial (10 pts)                        | Complete (20 pts)                                                          |
| --- | ------------------------------- | ------------------------------- | --------------------------------------- | -------------------------------------------------------------------------- |
| 1   | **Module Creation**             | Files missing                   | Files exist but lack valid `export`s    | `mathUtils.js` and `stringUtils.js` present with proper ES `export`s       |
| 2   | **Import Usage**                | No imports or wrong syntax      | Imports compile but incomplete          | Correct ES `import` statements used in `index.js`                          |
| 3   | **Functionality**               | Code crashes / wrong output     | Runs but some outputs incorrect         | All functions run and produce expected results                             |
| 4   | **Code Quality & Organization** | Unreadable or disorganized      | Adequate but inconsistent style         | Clear, idiomatic ES6 code; logical file structure                          |
| 5   | **Conceptual Understanding**    | Missing or off‑topic reflection | Reflection present but vague/inaccurate | README accurately explains ES modules vs CommonJS and justifies ES modules |
