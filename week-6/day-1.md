# Assignment (Week 6, Day 1): Setting Up Jest for React Testing

## Objective

- Create a **new React project** (Webpack & Babel) and **install Jest** for testing.
- Configure **basic test scripts** in `package.json`.
- Verify Jest runs a simple test successfully.

## Instructions

### Part 1 – New React Project Setup

1. **Create a project folder**

   - Example name: `react-jest-setup`
   - Inside that folder run `npm init -y` to create `package.json`.

2. **Start a React project**

   - Set up React any way you like (for example with Vite, a custom Webpack build, etc.).
   - Make sure the app builds and loads in a browser before you move on to testing.

---

### Part 2 – Install & Configure Jest

1. **Add testing dependencies**

   ```bash
   npm install --save-dev jest babel-jest @testing-library/react @testing-library/jest-dom
   ```

   - **jest** – test runner and assertion library
   - **babel-jest** – lets Jest work with Babel-transpiled code
   - **@testing-library/react** and **@testing-library/jest-dom** – helpers for React component tests

2. **Add a Jest script**

   In `package.json`:

   ```json
   "scripts": {
     "test": "jest"
   }
   ```

---

### Part 3 – Write a Simple Test

1. **Create a test file**

   - Place it in a `__tests__` or `tests` folder (or beside the component under `src`).
   - Example file name: `App.test.js`.

2. **Add a basic test**

   ```js
   test("basic math works", () => {
     expect(2 + 2).toBe(4);
   });
   ```

---

### Part 4 – Run Your Tests

1. **Execute Jest**

   ```bash
   npm test
   ```

2. **Check the output**

   - Passing tests will display green checks; failures will list errors to fix.

---

## Submission

- **GitHub repository**

  - Push your full project (source, config files, and tests).
  - Include a concise **README** with install, build, and test commands (`npm install`, `npm run build` or equivalent, `npm test`).

---

## Rubric

| Criteria                              | Limited (0 pts)                          | Partial (13 pts)                       | Complete (25 pts)                                                |
| ------------------------------------- | ---------------------------------------- | -------------------------------------- | ---------------------------------------------------------------- |
| **Custom React build setup**          | Build is broken or key files are missing | Build works but has configuration gaps | React project builds and runs cleanly                            |
| **Jest installation & script**        | Jest missing or test script absent       | Jest installed but mis-configured      | Jest fully set up and `npm test` runs successfully               |
| **Basic test implementation**         | No test file or tests never run          | Test file exists but fails to run      | At least one passing test visible in console                     |
| **Code organization & documentation** | Disorganized files, unclear instructions | Basic structure, minimal README        | Clear folder structure and helpful README (install, build, test) |
