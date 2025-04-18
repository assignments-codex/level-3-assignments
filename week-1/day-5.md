# Assignment 3 (Day 5): Node.js & NPM Review Project

## Objective

- Reinforce core Node.js skills: creating scripts, using modules, and working in the terminal.
- Demonstrate understanding of NPM basics: package installation, versioning, and scripts.
- Combine the knowledge from previous days into one small review project.

## Instructions

### Part 1: Project Setup

- Use your existing project folder named `node-review`.
- Ensure your `package.json` includes
  ```json
  "type": "module"
  ```
  so you can use `import`/`export` syntax.

---

### Part 2: Custom Module (`utils.js`)

- Create a file named `utils.js`.
- Export **two** utility functions of your choice (e.g. greeting, string/array transformer).

---

### Part 3: Main Script (`app.js`)

- Create `app.js`.
- Import your utilities from `utils.js` using ES Module syntax.
- Install and import **one** third‑party package (e.g. `lodash` or `inquirer`).
- Call each of your custom functions and demonstrate a feature from your chosen package.

---

### Part 4: NPM Script

- In `package.json`, add a `"start"` script to run `app.js`.
- Verify with:
  ```bash
  npm start
  ```
  that it runs without errors.

---

### Part 5: Submission Requirements

1. **GitHub Repository (required):**
   - Create a public repo named `node-review`.
   - Push **all** project files (`package.json`, `utils.js`, `app.js`, etc.).
   - Submit the **repo link**.
2. **Evidence of Success:**
   - Include a screenshot or terminal log showing:
     - Your project’s folder structure.
     - Successful execution of `npm start`.

---

### Grading Rubric

| Criterion                     | Missing / Incorrect         | Partially Complete                               | Fully Complete (25 pts)                                   |
| ----------------------------- | --------------------------- | ------------------------------------------------ | --------------------------------------------------------- |
| **ES Module Setup**           | Still using CommonJS        | `"type":"module"` added but not fully functional | ES Modules enabled and working correctly                  |
| **Custom Module & Imports**   | No `utils.js` or no exports | Functions exist but not correctly imported/used  | Two functions exported, imported, and used correctly      |
| **Third‑Party Package Usage** | Not installed or unused     | Installed but usage is minimal or incorrect      | Correct installation and meaningful feature demonstration |
| **Start Script**              | Missing or fails to run     | Exists but errors remain                         | Runs cleanly with `npm start`                             |
| **GitHub Repo Submission**    | No repo link provided       | Repo exists but missing files or link broken     | Public repo link provided with all files & clear README   |
