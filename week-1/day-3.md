# Assignment 2 (Day 3): Creating and Using JavaScript Modules

## Objective

- Learn how to create reusable JavaScript modules in Node.js.
- Practice importing and exporting functions across multiple files.
- Build a simple Node.js application that demonstrates modular code organization.

## Instructions

### Part 1: Project Setup

1. **Create a New Folder**
   - Name it `js-modules-practice`.
   - Open your terminal in this folder.
2. **Initialize NPM**

   - Run:

     `npm init -y`

   - This creates a `package.json` file (you may already be familiar with this from Day 2).

### Part 2: Create a Utility Module

1. **Create `mathUtils.js`**

   - Export at least two functions, e.g., `add(a, b)` and `subtract(a, b)`.
   - Example:

     `// mathUtils.js function add(a, b) {   return a + b; }  function subtract(a, b) {   return a - b; }  module.exports = {   add,   subtract };`

2. **Create `stringUtils.js`**

   - Export at least one function, e.g., `capitalize(str)` or `reverseString(str)`.
   - Example:


     `// stringUtils.js function capitalize(str) {   return str.charAt(0).toUpperCase() + str.slice(1); }  module.exports = {   capitalize };`

### Part 3: Build a Main Script

1. **Create `index.js`**

   - Import functions from `mathUtils.js` and `stringUtils.js`.
   - Example:


     `` const { add, subtract } = require('./mathUtils'); const { capitalize } = require('./stringUtils');  const num1 = 5; const num2 = 10; console.log(`Adding: ${num1} + ${num2} =`, add(num1, num2)); console.log(`Subtracting: ${num2} - ${num1} =`, subtract(num2, num1));  const phrase = "hello from node modules!"; console.log("Original:", phrase); console.log("Capitalized:", capitalize(phrase)); ``

2. **Run Your Program**

   - In your terminal, execute:

     `node index.js`

   - Verify the output for both the math operations and the string manipulation.

### Part 4: Experiment & Extend (Optional)

- Add **more utility functions** (e.g., multiply, divide, or advanced string methods).
- Create a **new module** (e.g., `arrayUtils.js`) and import it into `index.js`.
- If you want to go further, try using a **third-party library** from Day 2 (like Lodash) in one of your utility modules.

## Submission

- **GitHub Repository** (Optional):
  - Create a repository named `js-modules-practice`.
  - Commit and push your `index.js`, `mathUtils.js`, `stringUtils.js`, and `package.json`.
- **Submission Link**:
  - Provide the GitHub repo link.

## Rubric

| Criteria                        | Limited (0 pts)                                 | Partial (3 pts)                                                         | Complete (5 pts)                                                                 |
| ------------------------------- | ----------------------------------------------- | ----------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **Module Creation**             | No separate modules created                     | Modules created but incomplete or incorrectly structured                | Separate modules (`mathUtils.js`, `stringUtils.js`) created with correct exports |
| **Import/Export Usage**         | No imports/exports used or incorrectly used     | Imports/exports used but with errors or missing functionality           | Correctly imports/exports functions and demonstrates usage in `index.js`         |
| **Functionality**               | Functions do not run or yield incorrect results | Functions run but partially, or do not cover basic math/string examples | Functions produce correct results for both math and string utilities             |
| **Code Quality & Organization** | Code is difficult to read or poorly structured  | Code is somewhat organized but could be cleaner                         | Code is well-organized, easy to read, and logically separated across modules     |
