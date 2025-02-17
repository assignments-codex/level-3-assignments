# Task (Day 2): Using NPM and Exploring Lodash & Inquirer

## Objective

- Practice initializing a Node.js project and managing packages with **NPM**.
- Get hands-on with **Lodash** for utility functions.
- Explore **Inquirer** for interactive command-line prompts.

## Instructions

### Part 1: Project Setup & NPM Basics

1. **Initialize a New Project**

   - Create a new folder (e.g., `npm-exploration`).
   - In your terminal, navigate to that folder and run:

     `npm init -y`

   - This will create a `package.json` file with default settings.

2. **Inspect package.json**
   - Open the `package.json` file in your code editor.
   - Note the default properties like `name`, `version`, `main`, etc.

### Part 2: Installing and Using Lodash

1. **Install Lodash**

   - Run:

     `npm install lodash`

   - Verify `lodash` appears under **dependencies** in `package.json`.

2. **Use Lodash in a Script**

   - Create a new file named `lodash-demo.js`.
   - Add the following code (or something similar) to test a Lodash function:

     `const _ = require('lodash');  const array = [1, 2, 3, 4, 5]; const reversed = _.reverse([...array]); // using spread to avoid mutating the original console.log("Original:", array); console.log("Reversed:", reversed);`

   - Run the script with:

     `node lodash-demo.js`

   - Observe the output.

### Part 3: Installing and Using Inquirer

1. **Install Inquirer**

   - Run:

     `npm install inquirer`

2. **Create an Inquirer Prompt**

   - Create a new file named `inquirer-demo.js`.
   - Use Inquirer to ask a simple question:

     `` const inquirer = require('inquirer');  inquirer   .prompt([     {       type: 'input',       name: 'userName',       message: 'What is your name?',     }   ])   .then((answers) => {     console.log(`Hello, ${answers.userName}!`);   })   .catch((error) => {     console.error("An error occurred:", error);   }); ``

   - Run the script:

     `node inquirer-demo.js`

   - Enter a name at the prompt and verify the output.

---

## Additional Notes

> - This is a **non-graded** task. Focus on **understanding NPM workflows**, **basic Lodash functions**, and **interactive prompts with Inquirer**.
> - If you have extra time, consider exploring more Lodash functions (e.g., `_.chunk`, `_.random`) or adding more questions in Inquirer.
