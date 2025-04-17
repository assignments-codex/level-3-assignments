# Task (Week 1, Day 4): Preparing and Publishing a Simple Package to NPM

## Objective

- Understand the steps required to create and publish an NPM package.
- Practice versioning and package naming conventions.
- Gain familiarity with the `npm publish` workflow (using a test package).

### Part 1: Project Setup

1. **Create a New Folder**

   - Name it `my-first-npm-package`.

   - Open your terminal in that folder.

2. **Initialize the Project**

   ```bash
   npm init -y
   ```

   This generates a `package.json` with default settings.

3. **Enable ES Modules**

   - Open `package.json` and add:

     ```json
     {
       "type": "module",
       …
     }
     ```

   - This tells Node.js to treat `.js` files as ES modules.

---

### Part 2: Write Your Library

1. **Create a `src` Directory (Optional but Recommended)**

   ```bash
   mkdir src
   ```

2. **Add a Greeting Function**

   - Create `src/index.js` with ES6 syntax:

     ```js
     export function greet(name) {
       return `Hello, ${name}! This is my first npm package.`;
     }
     ```

3. **Point `main` to Your Entry File**
   In `package.json`, ensure:

   ```json
   {
     "main": "src/index.js",
     …
   }
   ```

---

### Part 3: Prepare for Publishing

1. **Pick a Unique Package Name**

   - The `"name"` field in `package.json` must be unique on npm.

   - If you get a naming conflict, append something unique (e.g. `-xyz`) to your name.

2. **Add a `.gitignore`**

   ```gitignore
   node_modules
   ```

3. **Log In to npm**

   ```bash
   npm login
   ```

   Follow prompts for username, password, and email.

---

### Part 4: Publish Your Package

1. **Dry Run (Optional)**

   ```bash
   npm publish --dry-run
   ```

   - Checks for publish errors without actually publishing.

2. **Publish**

   ```bash
   npm publish
   ```

   - If successful, your package is live on npm.

3. **Versioning for Updates**

   - Bump the `"version"` in `package.json` (e.g. `"1.0.0"` → `"1.0.1"`).

   - Run `npm publish` again.

---

### Part 5: Test Your Package

1. **Create a New Test Project**

   ```bash
   mkdir test-greet
   cd test-greet
   npm init -y
   npm install my-first-npm-package
   ```

2. **Use Your Package**
   Create `test.js`:

   ```js
   import { greet } from "my-first-npm-package";

   console.log(greet("World"));
   ```

3. **Run the Test**

   ```bash
   node test.js
   ```

   You should see:

   ```sh

   Hello, World! This is my first npm package.
   ```
