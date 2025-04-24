# Assignment 1 (Week 2, Day 1): Introduction to Webpack & Basic Setup

## Objective

- Understand what Webpack is and why it's used in modern web development.
- Set up a basic Webpack configuration to bundle multiple JavaScript files into one output.

## Instructions

### Part 1: Project Initialization

1. **Create a New Folder**

- Name it `webpack-intro`.

- Open your terminal in that folder.

2. **Initialize NPM**

`bash
    npm init -y
`

This creates a `package.json`.

3. **Enable ES Modules**
   In your `package.json`, add `"type": "module"` at the top level:

`jsonc
    {
      "type": "module",
      }
`

---

### Part 2: Install Webpack

```bash
npm install --save-dev webpack webpack-cli
```

> Verify that `webpack` and `webpack-cli` appear under `devDependencies` in `package.json`.

---

### Part 3: Create Your Source Files

1. **Make a `src/` Folder**

2. **Add Two Files**

- `src/greetings.js`

- `src/index.js`

3. **Populate Them with ES Modules**

```js
export function sayHello(name) {
  return `Hello, ${name}!`;
}

export function sayGoodbye(name) {
  return `Goodbye, ${name}!`;
}
```

```js
import { sayHello, sayGoodbye } from "./greetings.js";

console.log(sayHello("Webpack"));
console.log(sayGoodbye("Webpack"));
```

### Part 4: Basic Webpack Configuration (ES Modules)

1. **Create** `webpack.config.js` **at the project root**

2. **Use ES Module Syntax** (requires `"type": "module"` in `package.json`):

```js

import path from 'path';
    import { fileURLToPath } from 'url';



const **filename = fileURLToPath(import.meta.url);
   const **dirname = path.dirname(\_\_filename);

export default {
    entry: './src/index.js',
    output: {
      path: path.resolve(\_\_dirname, 'dist'),
       filename: 'bundle.js'
      },
      mode: 'development'
    };
```

### Part 5: Build & Test

1. **Add a Build Script**
   In `package.json` → `"scripts"`:

`json
   "scripts": {
    "build": "webpack"
   }
    `

2. **Run the Build**

`bash
   npm run build
   `

- A `dist/` folder should appear containing `bundle.js`.

- Check the terminal for errors; inspect `bundle.js` if needed.

### Part 6: Verify in a Browser

1. **Create** `index.html` **in the root**:

```html
<!DOCTYPE html>

<html>
       
  <head>
           
    <meta charset="UTF-8" />
           
    <title>Webpack Intro</title>
         
  </head>
       
  <body>
           
    <script src="./dist/bundle.js"></script>
         
  </body>
     
</html>
```

2. **Open** `index.html` **in your browser**  
       – Watch the console for “Hello, Webpack!” and “Goodbye, Webpack!”

## Submission

1. **GitHub Repo**: Create a new repo named `webpack-intro`.

2. **Commit & Push**:

- `package.json` & `package-lock.json`

- `webpack.config.js`

- `src/` folder (`index.js`, `greetings.js`)

- _(Optional)_ `index.html` if tested in-browser

3. **Submit** the repo link on the assignment platform.

## Rubric

| Criteria                           | 0 pts                      | 10 pts                                  | 20 pts                                                               |
| ---------------------------------- | -------------------------- | --------------------------------------- | -------------------------------------------------------------------- |
| **Webpack Installation**           | Not installed              | Installed but mis‑configured            | Properly installed (`devDependencies`), verified in `package.json`   |
| **Project Structure & Config**     | Missing or broken config   | Config present with errors              | Clear structure, working ES‑module `webpack.config.js`               |
| **Bundling & Scripts**             | No build script or fails   | Builds with warnings or partial output  | `npm run build` succeeds, produces valid `dist/bundle.js`            |
| **Code Organization & Execution**  | Errors or no console logs  | Runs but minor import/export issues     | Clean ES modules, logs correct output, demonstrates imports/exports  |
| ** Browser Test**                  | Not attempted              | Opened but no console verification      | Successfully tested in-browser; console shows expected messages      |
