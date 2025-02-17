# Assignment 3 (Week 2, Day 5): Webpack & Babel Review Project

## Objective

- Consolidate your knowledge of **Webpack** and **Babel**.
- Create a small, buildable web project that uses modern JavaScript features.
- Practice organizing a front-end toolchain in a clear and professional manner.

## Instructions

### Part 1: Project Setup

1. **Create a Folder**
   - Name it something like `webpack-babel-review`.
2. **Initialize NPM**

   - From inside that folder, run:

     `npm init -y`

   - A `package.json` file should be generated.

### Part 2: Install and Configure Webpack

1. **Install Packages**
   - Install `webpack` and `webpack-cli` as dev dependencies.
2. **Create Your Webpack Config**
   - Add a `webpack.config.js` with:
     - An **entry** file (e.g., `src/index.js`).
     - An **output** file (e.g., `dist/bundle.js`).
     - A `mode` setting (development or production).
   - Include a **rule for JavaScript** if you plan on using Babel within Webpack.

### Part 3: Integrate Babel

1. **Install Babel Packages**
   - Typically `@babel/core`, `@babel/preset-env`, and `babel-loader`.
2. **Set Up Babel**
   - Add a Babel configuration (`.babelrc`, `babel.config.js`, or within `package.json`) referencing the necessary preset(s).
   - Ensure your Webpack config uses `babel-loader` on `.js` files so that modern JS features are transpiled.

### Part 4: Write Your Code

1. **Create a `src` Folder**
   - Inside it, add an `index.js` that uses a few **modern JavaScript features** (arrow functions, optional chaining, destructuring, etc.).
2. **Add an HTML File**
   - Reference the output bundle (e.g., `<script src="./dist/bundle.js"></script>`).
   - This ensures you can load the transpiled code in a browser.

### Part 5: Build and Verify

1. **Add a Script**
   - In `package.json`, include a `"build": "webpack"` script under `"scripts"`.
2. **Run Your Build**
   - Execute `npm run build` to produce the `dist` folder with the bundled code.
3. **Test in a Browser**
   - Open your HTML file and check the console to ensure your modern JS features are executing correctly in the transpiled output.

---

## Submission

- **GitHub Repository**
  1. Create a repo named `webpack-babel-review`.
  2. Commit and push:
     - `package.json`, `webpack.config.js`, and all Babel-related config files.
     - Your `src` folder with modern JS code.
     - Your `dist` folder if requested, or if you prefer to include build artifacts.
     - An HTML file that references the bundled code.
- **Submission Link**
  - Provide your GitHub repository URL through the usual submission method.

---

## Rubric

| Criteria                           | Limited (0 pts)                               | Partial (3 pts)                                          | Complete (5 pts)                                                                               |
| ---------------------------------- | --------------------------------------------- | -------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **Webpack Setup**                  | No Webpack config or config is non-functional | Webpack config exists but incomplete or error-prone      | Webpack config properly set, with clear entry/output and a functioning build                   |
| **Babel Integration**              | No Babel setup or code not transpiled         | Some Babel setup, but partial/incorrect usage            | Babel fully integrated; modern JS features are correctly transpiled                            |
| **Modern JavaScript Usage**        | Only older JS syntax used                     | Some ES6+ features used, but minimal                     | Multiple modern features (arrow functions, destructuring, optional chaining, etc.)             |
| **Code Organization & Structure**  | Disorganized or missing files/folders         | Basic structure present but somewhat unclear             | Well-structured folder layout with a clear `src` and build artifacts in `dist`                 |
| **Deployment & GitHub Submission** | No GitHub repo link provided                  | Repo link given but incomplete or missing required files | Repository link provided with all required files; deployed according to instructions in course |
