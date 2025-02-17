# Assignment 3 (Day 5): Node.js & NPM Review Project

## Objective

- Reinforce core Node.js skills: creating scripts, using modules, and working in the terminal.
- Demonstrate understanding of NPM basics: package installation, versioning, and scripts.
- Combine the knowledge from previous days into one small review project.

## Instructions

### Part 1: Project Initialization

1. **Create a New Folder**
   - Name it `node-review`.
   - Open your terminal in this folder.
2. **Initialize NPM**

   - Run:

     `npm init -y`

   - Confirm a `package.json` file is created.

### Part 2: Combine Previous Concepts

1. **Create a Main Script**
   - Name it `app.js`.
   - This script should do **all** of the following:
     - Import and use a **custom module** (e.g., a `utils.js` file).
     - Use one **third-party package** (Lodash or Inquirer, etc.).
2. **Write a Custom Module**
   - Name it `utils.js`.
   - Export at least one function. For example, a function that returns a greeting message or manipulates an array/string.

### Part 3: Implement the Logic

1. **In `app.js`,**

   - Require (`const ... = require(...)`) the function from `utils.js`.
   - Install and require a third-party package (e.g., `lodash` or `inquirer`).
   - Use **both** the custom module’s function **and** the third-party package in some way:

     `// app.js const { myUtility } = require('./utils'); const _ = require('lodash'); // Example using Lodash  // Custom function usage console.log("My Utility Output:", myUtility("Hello World"));  // Third-party package usage (Lodash example) const nums = [4, 5, 6, 7]; const reversed = _.reverse([...nums]); console.log("Original:", nums); console.log("Reversed:", reversed);`

   - (If you choose Inquirer, prompt the user for input and then pass the result to your utility function.)

### Part 4: Add NPM Scripts (Optional Enhancement)

2. **In `package.json`,**

   - Under `"scripts"`, add a `"start"` script to run `app.js`:

     `"scripts": {   "start": "node app.js" }`

3. **Test the Script**

   - Run:

     `npm start`

   - Verify everything works as expected.

### Part 5: Show Your Work (Screenshot or Logs)

- Capture a screenshot (if requested) or copy/paste the **terminal output** showing:
  1. The project folder structure.
  2. Successful run of `npm start` or `node app.js`.

## Submission

- **GitHub Repository** (Optional):
  - Create a repo named `node-review` and upload your code.
- **Submission Link**:
  - Provide the GitHub repo link.

## Rubric

| Criteria                                 | Limited (0 pts)                                        | Partial (3 pts)                                     | Complete (5 pts)                                                           |
| ---------------------------------------- | ------------------------------------------------------ | --------------------------------------------------- | -------------------------------------------------------------------------- |
| **NPM Project Setup**                    | No package.json or script usage                        | package.json exists but minimal scripts             | Proper package.json with at least a start script                           |
| **Custom Module & Import**               | No custom module created or incorrect module usage     | Custom module created but partially implemented     | Custom module properly exports/imports a function                          |
| **Third-Party Package Usage**            | No third-party package or incorrect usage              | Installed but poorly implemented or minimal usage   | Correctly installs and uses a package (Lodash, Inquirer, etc.) in the code |
| **Overall Functionality & Organization** | Script doesn’t run, errors present, or code is unclear | Script runs but partial functionality or messy code | Script runs, code is organized, and all features work as intended          |
