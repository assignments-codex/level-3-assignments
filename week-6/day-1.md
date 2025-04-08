# Assignment (Week 6, Day 1): Setting Up Jest for React Testing

## Objective

- Create a **new React project** (Webpack & Babel) and **install Jest** for testing.
- Configure **basic test scripts** in `package.json`.
- Verify Jest runs a simple test successfully.

## Instructions

### Part 1: New React Project Setup

1. **Create a New Folder**
   - For example, `react-jest-setup`.
   - Initialize a Node.js project with `npm init -y`.
2. **Install React & Build Tools**
   - Use **Webpack**, **Babel**, and **React** as demonstrated in prior weeks (Week 3, Day 1).
   - Make sure you can build and view your React app in the browser before adding Jest.

### Part 2: Install & Configure Jest

1. **Install Jest & Related Packages**

   ```bash
   npm install --save-dev jest babel-jest @testing-library/react @testing-library/jest-dom
   ```

   - **Jest**: The test runner and assertion library.
   - **babel-jest**: Allows Jest to work with Babel-transpiled code.
   - **@testing-library/react** and **@testing-library/jest-dom**: Tools for testing React components in Jest.

2. **Add Jest Config**

   - In your `package.json`, under `"scripts"`, add:

     ```json
     "scripts": {
       "test": "jest"
     }
     ```

   - Optionally, create a **`jest.config.js`** file (if needed for custom configs) or rely on Jest defaults.

### Part 3: Write a Simple Test

1. **Create a Test File**
   - For example, make a `__tests__` folder or `tests` folder in your project root or inside `src`.
   - Name it something like `App.test.js` or `sum.test.js`.
2. **Write a Basic Test**

   - Example pseudocode:

     ```js
     test("Basic math test", () => {
       expect(2 + 2).toBe(4);
     });
     ```

### Part 4: Run Your Tests

1. **Execute Jest**
   - Run `npm test` in your terminal.
2. **Verify Success**
   - The command should show passing or failing tests in the console.
   - If tests fail, review any error messages.

---

## Submission

- **GitHub Repository**
  - Create a new repo (e.g., `react-jest-setup`).
  - Include **webpack.config.js**, **.babelrc**, `package.json`, and **test file(s)**.
  - Provide a **README** describing installation, build, and test steps (e.g., `npm install`, `npm run build`, `npm test`, etc.).

---

## Rubric

| Criteria                               | Limited (0 pts)                                | Partial (10 pts)                                     | Complete (20 pts)                                                          |
| -------------------------------------- | ---------------------------------------------- | ---------------------------------------------------- | -------------------------------------------------------------------------- |
| **Manual React Setup (Webpack/Babel)** | Build is broken or missing essential files     | Partially configured with errors or missing pieces   | Fully operational Webpack/Babel React project (compiles, runs, tested)     |
| **Jest Installation & Config**         | No test script or Jest not installed correctly | Jest installed but incomplete config or usage        | Jest fully installed; `"test"` script in `package.json` runs successfully  |
| **Basic Test Implementation**          | No test file or tests never run                | Test file exists but fails to run or incomplete test | At least one working test that shows pass/fail in the console              |
| **Code Organization & Documentation**  | Disorganized files, unclear instructions       | Basic structure, missing some clarity in README      | Clear folder structure, helpful README (install, build, test instructions) |
