# Task (Week 1, Day 4): Preparing and Publishing a Simple Package to NPM

## Objective

- Understand the steps required to create and publish an NPM package.
- Practice versioning and package naming conventions.
- Gain familiarity with the `npm publish` workflow (using a test package).

## Instructions

### Part 1: Project Setup

1. **Create a New Folder**
   - Name it `my-first-npm-package`.
   - Open your terminal in this folder.
2. **Initialize NPM**

   - Run:

     `npm init -y`

   - A `package.json` file is generated.

### Part 2: Write a Simple Library

1. **Create a `src` Folder** (optional but organized)
   - Inside `my-first-npm-package`, create a folder named `src`.
2. **Add a Simple Function**

   - In `src`, create `index.js`:

     `` // src/index.js function greet(name) {   return `Hello, ${name}! This is my first npm package.`; }  module.exports = greet; ``

3. **Update `package.json`**

   - Ensure the `"main"` field points to your library’s entry file. For example:

     `{   "name": "my-first-npm-package",   "version": "1.0.0",   "main": "src/index.js",   ... }`

### Part 3: Prepare for Publishing

4. **Choose a Unique Name**
   - The `"name"` field in `package.json` must be unique on NPM.
   - If you get an error when publishing, rename your package (e.g., `"my-first-npm-package-xyz"`).
5. **Add a `.gitignore`** (Optional but recommended)

   - If you have a GitHub repo, ignore `node_modules`:

     `node_modules`

6. **Login to NPM**

   - If you haven’t already, create an NPM account at [npmjs.com](https://www.npmjs.com/).
   - In your terminal:

     `npm login`

   - Provide your username, password, and email.

### Part 4: Publish to NPM

7. **Dry Run** (Optional)

   - Check for any potential issues before publishing:

     `npm publish --dry-run`

8. **Publish**

   - If everything looks good:

     `npm publish`

   - You should see a success message indicating your package is published.

9. **Versioning**
   - If you make changes later, update the `"version"` in `package.json` (e.g., from `1.0.0` to `1.0.1`) before running `npm publish` again.

### Part 5: Test Your Package (Optional)

10. **Create a Test Project** in a separate folder:

    `npm init -y npm install my-first-npm-package`

11. **Use the Package**:

    `// test.js const greet = require('my-first-npm-package'); console.log(greet("World"));`

12. **Run**:

    `node test.js`

    - Verify it logs the greeting message.

---

## Additional Notes

- This is a **non-graded task**; however, if you’d like to showcase your work, you can:
  - Create a **GitHub repository** named `my-first-npm-package`.
  - Commit and push your files (`package.json`, `.gitignore`, `src/index.js`).
- Remember: **once a package is public on NPM, anyone can install it** (unless you use private packages with a paid plan).
- If you don’t want to keep your test package on NPM, you can **unpublish** it, but be cautious: there are [NPM unpublish policies](https://docs.npmjs.com/policies/unpublish).
