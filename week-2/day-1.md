# Assignment 1 (Week 2, Day 1): Introduction to Webpack & Basic Setup

## Objective

- Understand what Webpack is and why it’s used in modern web development.
- Set up a basic Webpack configuration to bundle multiple JavaScript files into one output.

## Instructions

### Part 1: Project Initialization

1. **Create a New Folder**
   - Name it `webpack-intro`.
   - Open your terminal inside this folder.
2. **Initialize NPM**

   - Run:

     `npm init -y`

   - Confirm that a `package.json` file is created in your folder.

### Part 2: Install Webpack

1. **Install Webpack & Webpack CLI**

   - Run:

     `npm install --save-dev webpack webpack-cli`

   - Verify that `webpack` and `webpack-cli` appear under `devDependencies` in `package.json`.

### Part 3: Create Your Source Files

2. **Make a `src` Folder**
   - Inside `webpack-intro`, create a folder named `src`.
3. **Add JavaScript Files**
   - Within `src`, create two files:
     - `index.js`
     - `greetings.js`
4. **Populate the Files**

   - `greetings.js`:

     `` export function sayHello(name) {   return `Hello, ${name}!`; }  export function sayGoodbye(name) {   return `Goodbye, ${name}!`; } ``

   - `index.js`:

     `import { sayHello, sayGoodbye } from './greetings.js';  console.log(sayHello("Webpack")); console.log(sayGoodbye("Webpack"));`

### Part 4: Basic Webpack Configuration

5. **Create `webpack.config.js`**

   - At the root of `webpack-intro`, create a file named `webpack.config.js`:

     `const path = require('path');  module.exports = {   entry: './src/index.js',   output: {     path: path.resolve(__dirname, 'dist'),     filename: 'bundle.js'   },   mode: 'development' };`

   - **Explanation**:
     - `entry` specifies the main JavaScript file (`index.js`).
     - `output` defines the bundle’s destination (`dist/bundle.js`).
     - `mode: 'development'` enables easier debugging.

### Part 5: Run Webpack & Test

6. **Add a Build Script**

   - In `package.json`, under `"scripts"`, add:

     `"scripts": {   "build": "webpack" }`

7. **Build the Project**

   - Run:

     `npm run build`

   - A `dist` folder should appear, containing `bundle.js`.

8. **Verify Output**
   - Optionally inspect `dist/bundle.js` (it may look minified).
   - Check the terminal for any errors or warnings.

### Part 6: (Optional) Test in a Browser

9. **Create a Basic HTML File**

   - In the root directory, create `index.html`:

     `<!DOCTYPE html> <html> <head>   <meta charset="UTF-8" />   <title>Webpack Intro</title> </head> <body>   <script src="./dist/bundle.js"></script> </body> </html>`

10. **Open `index.html`**
    - Check the browser’s console for the messages from `index.js`.

---

## Submission (GitHub Only)

11. **Create a New GitHub Repository** named `webpack-intro`.
12. **Commit and Push**:
    - `package.json` and `package-lock.json`
    - `webpack.config.js`
    - The `src` folder (with `index.js` and `greetings.js`)
    - (Optional) `index.html` if you tested in a browser
13. **Submit the Repository Link** through the designated platform.

---

## Rubric

| Criteria                          | Limited (0 pts)                                         | Partial (3 pts)                                      | Complete (5 pts)                                                              |
| --------------------------------- | ------------------------------------------------------- | ---------------------------------------------------- | ----------------------------------------------------------------------------- |
| **Webpack Installation**          | Webpack/CLI not installed or project not initialized    | Installed but configuration incomplete or incorrect  | Properly installed `webpack` & `webpack-cli`, verified in `devDependencies`   |
| **Project Structure & Config**    | Unclear or missing `webpack.config.js`                  | Has a config file but with errors or missing details | Clear project structure with a working `webpack.config.js`                    |
| **Bundling & Scripts**            | Code does not bundle; no build script in `package.json` | Bundling partially works or script is incomplete     | Bundling successful via `npm run build` and produces a valid `dist/bundle.js` |
| **Code Organization & Execution** | Errors when running bundled code or no console output   | Bundled code runs but with minor issues              | Code runs as expected, logs output in console, demonstrates import/exports    |
| **Optional Browser Test** (Bonus) | No attempt to open in a browser or check console        | Attempt made but incomplete verification             | Successfully tested in a browser; console logs “Hello, Webpack!” messages     |
