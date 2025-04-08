# Assignment (Week 3, Day 1): Setting Up React.js from Scratch with Webpack and Babel

## Objective

- Learn how to set up a **React.js** project **manually** without using create-react-app.

- Configure **Webpack** and **Babel** to bundle and transpile modern JavaScript (including JSX).

- Verify that a simple React component can render in the browser.

## Instructions

### Part 1: Project Initialization and Dependencies

1. **Create a New Folder**

   - Make a folder named `react-webpack-babel-setup` (or a similar descriptive name).

   - Initialize a new Node.js project by running `npm init -y` inside that folder.

2. **Install React and Other Dependencies**

   - Install React and React DOM as regular dependencies:

     ```bash
     npm install react react-dom
     ```

   - Install Webpack and Babel as development dependencies:

     ```bash
     npm install --save-dev webpack webpack-cli babel-loader @babel/core @babel/preset-env @babel/preset-react
     ```

3. **Confirm package.json**

   - Open `package.json` and confirm that `react` and `react-dom` are in **dependencies**, and Webpack/Babel packages are in **devDependencies**.

### Part 2: Basic Webpack and Babel Configuration

4. **Create `webpack.config.js`**

   - In the root of your folder, create a file named `webpack.config.js` with the following starter content:

     ```js
     const path = require("path");

     module.exports = {
       entry: "./src/index.js",
       output: {
         path: path.resolve(__dirname, "dist"),
         filename: "bundle.js",
       },
       module: {
         rules: [
           {
             test: /\.js$/,
             exclude: /node_modules/,
             use: {
               loader: "babel-loader",
             },
           },
         ],
       },
       mode: "development", // or 'production'
     };
     ```

5. **Set Up Babel**

   - Create a file named `.babelrc` (or `babel.config.json`) in the project root:

     ```json
     {
       "presets": ["@babel/preset-env", "@babel/preset-react"]
     }
     ```

### Part 3: Create and Bundle a React Component

6. **Create Your Source Files**

   - Inside a new folder called `src`, create two files:

     - `index.js`

     - `App.js`

   - **`App.js`** (simple React component):

     ```js
     import React from "react";

     function App() {
       return (
         <div>
           <h1>Hello from a Manually Setup React App!</h1>
         </div>
       );
     }

     export default App;
     ```

   - **`index.js`** (entry point):

     ```js
     import React from "react";
     import ReactDOM from "react-dom/client";
     import App from "./App";

     const root = ReactDOM.createRoot(document.getElementById("root"));
     root.render(<App />);
     ```

7. **Create an HTML File**

   - In the **root** folder (or a separate `public` folder if you prefer), create `index.html`:

     ```html
     <!DOCTYPE html>
     <html lang="en">
       <head>
         <meta charset="UTF-8" />
         <meta
           name="viewport"
           content="width=device-width, initial-scale=1.0"
         />
         <title>Manual React Setup</title>
       </head>
       <body>
         <div id="root"></div>
         <script src="dist/bundle.js"></script>
       </body>
     </html>
     ```

### Part 4: Build and Test

8. **Add a Build Script**

   - In your `package.json`, under `scripts`, add:

     ```json
     "scripts": {
       "build": "webpack"
     }
     ```

   - Run `npm run build`. This should create a `dist` folder containing `bundle.js`.

9. **Open `index.html`**

   - Open `index.html` in your browser (via a simple local server or directly in the file system).

   - Confirm you see “Hello from a Manually Setup React App!” on the page.

---

## Submission

- **GitHub Repository**:

  - Name the repository `react-webpack-babel`.

  - Include all files (`src`, `webpack.config.js`, `.babelrc`, `index.html`, etc.).

- **Submission Link**:

  - Provide a link to your GitHub repository.

---

## Rubric

| Criteria                          | Limited (0 pts)                                         | Partial (10 pts)                                              | Complete (20 pts)                                                  |
| --------------------------------- | ------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Webpack & Babel Configuration** | No config or incorrect setup; cannot build successfully | Partial config; builds with errors or warnings                | Correct config; project builds successfully without major errors   |
| **React Component Creation**      | No usable components or code does not compile           | Basic component(s) created but missing key functionality      | Clear, functional component(s) that compile and render as expected |
| **File & Folder Structure**       | Files missing or disorganized                           | Basic organization but some files out of place                | Logical structure (`src`, `dist`, etc.); easy to navigate          |
| **Successful Build & Output**     | Project doesn’t build or run in the browser             | Build succeeds but output not fully functional in the browser | Build and bundle succeed; content loads correctly in the browser   |
| **Code Quality and Organization** | Code is hard to follow or uses poor naming conventions  | Code somewhat clear but lacks consistent style or structure   | Code follows best practices, is well-organized, and easy to read   |
