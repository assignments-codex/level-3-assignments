# Assignment (Week 5, Day 1): Introduction to SASS with Nesting and Variables

## Objective

1. Set up a **new React project** using **Webpack** and **Babel**.

2. Configure **SASS** compilation and demonstrate **nesting** plus **variables** in `.scss` files.

## Instructions

### Part 1: Initial Project Setup

1. **Create a New Folder** (`sass-nesting-variables`) and run:

   ```bash
   npm init -y
   ```

2. **Install React**:

   ```bash
   npm install react react-dom
   ```

3. **Install Dev Dependencies**:

   ```bash
   npm install --save-dev webpack webpack-cli babel-loader @babel/core @babel/preset-env @babel/preset-react sass sass-loader style-loader css-loader
   ```

### Part 2: Babel Configuration

1. **Create a `.babelrc`** in your project root:

   ```json
   {
     "presets": ["@babel/preset-env", "@babel/preset-react"]
   }
   ```

### Part 3: Webpack Configuration

1. **Create a `webpack.config.js`** file in your project root with **exactly** the following content:

   ```js
   const path = require("path");

   module.exports = {
     entry: "./src/index.js",
     output: {
       path: path.resolve(__dirname, "dist"),
       filename: "bundle.js",
     },
     mode: "development",
     module: {
       rules: [
         {
           test: /\.jsx?$/,
           exclude: /node_modules/,
           use: {
             loader: "babel-loader",
           },
         },
         {
           test: /\.scss$/,
           use: ["style-loader", "css-loader", "sass-loader"],
         },
       ],
     },
     resolve: {
       extensions: [".js", ".jsx"],
     },
   };
   ```

### Part 4: Project Structure & SASS Usage

1. **Create a `src` folder** for your React and SASS files.

2. **Ensure you have**:

   - An **entry point** file (e.g., `index.js`) that renders a minimal React component.

   - A **`.scss` file** with at least one **variable** and a **nested** rule.

   - An **import** statement referencing your `.scss` in your React code, so Webpack will compile it.

3. **Create an HTML file** that references the output bundle (`dist/bundle.js`).

### Part 5: Build & Test

1. **Run Webpack** to build:

   ```bash
   npx webpack
   ```

2. **Open your HTML file** (where `bundle.js` is linked). Confirm the SASS-based styles are applied to your React component.

---

## Submission

- **GitHub Repository**:

  - Create or use a new repository named something like `react-sass-intro`.

  - Include your **webpack.config.js**, **.babelrc**, `src` files, and HTML.

  - Add a **README** with the steps needed to install, build, and run the project.

---

## Rubric

| Criteria                             | Limited (0 pts)                                            | Partial (10 pts)                                                   | Complete (20 pts)                                                             |
| ------------------------------------ | ---------------------------------------------------------- | ------------------------------------------------------------------ | ----------------------------------------------------------------------------- |
| **Manual Webpack/Babel React Setup** | Broken or incomplete; cannot build/run app                 | Partially configured, with some errors or missing steps            | Fully configured Webpack/Babel stack, builds and runs as described            |
| **SASS Integration**                 | `.scss` is not handled or fails to compile                 | SASS partially set up; errors or missing some loader configuration | `.scss` compiles successfully; style-loader, css-loader, and sass-loader work |
| **Nesting & Variables in SASS**      | No nesting or variable usage                               | Minimal attempt but not clearly demonstrated                       | Clear nesting structure and at least one variable used in `.scss`             |
| **Code Organization & Clarity**      | Files missing, unclear structure, or no build instructions | Some structure, but incomplete README or file organization         | Logical file layout; README details how to install, build, and run            |
| **React Integration**                | No `.scss` import or styles never applied in React         | .scss is imported but partially or incorrectly applied             | .scss is imported, styles are confirmed visible in the rendered component     |
