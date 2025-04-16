# Task (Day 2): Using NPM and Exploring Lodash & Inquirer

## Objective

- Practice initializing a Node.js project and managing packages with **NPM**.
- Get hands-on with **Lodash** for utility functions.
- Explore **Inquirer** for interactive command-line prompts.

### Part 1: Project Setup & NPM Basics

1. **Initialize a New Project**

   - Create a new folder (`npm-exploration`).
   - In your terminal, navigate to that folder and run:

     ```bash
     npm init -y
     ```

   - This will create a `package.json` file with default settings.

2. **Enable ES Modules**

   - Open the `package.json` file in your code editor.
   - Add or edit the `"type"` property:

     ```json
     {
       "name": "npm-exploration",
       "version": "1.0.0",
       "type": "module",
       ...
     }
     ```

   - This tells Node.js to treat your `.js` files as ES modules.
   - **Note**: If you prefer not to set `"type": "module"`, you can name your files with the `.mjs` extension and still use ES6 `import` syntax.

3. **Inspect package.json**

   - Look at the default properties like `name`, `version`, `main`, etc.
   - Notice any changes after adding new dependencies (e.g., `lodash`, `inquirer`).

---

### Part 2: Installing and Using Lodash

1. **Install Lodash**

   - Run:

     ```bash
     npm install lodash
     ```

   - Verify `lodash` appears under **dependencies** in `package.json`.

2. **Use Lodash in a Script**

   - Create a new file named `lodash-demo.js`.
   - Add the following code to test a Lodash function **using ES6 imports**:

     ```js
     import _ from "lodash";

     const array = [1, 2, 3, 4, 5];
     const reversed = _.reverse([...array]);

     console.log("Original:", array);
     console.log("Reversed:", reversed);
     ```

   - Run the script with:

     ```bash
     node lodash-demo.js
     ```

   - Observe the output.

---

### Part 3: Installing and Using Inquirer

1. **Install Inquirer**

   - Run:

     ```bash
     npm install inquirer
     ```

   - Verify `inquirer` appears under **dependencies** in `package.json`.

2. **Create an Inquirer Prompt**

   - Create a new file named `inquirer-demo.js`.
   - Use Inquirer to ask a simple question **with ES6 imports**:

     ```js
     import inquirer from "inquirer";

     async function askUserName() {
       try {
         const answers = await inquirer.prompt([
           {
             type: "input",
             name: "userName",
             message: "What is your name?",
           },
         ]);
         console.log(`Hello, ${answers.userName}!`);
       } catch (error) {
         console.error("An error occurred:", error);
       }
     }

     askUserName();
     ```

   - Run the script:

     ```bash
     node inquirer-demo.js
     ```

   - Enter a name at the prompt and verify the output.
