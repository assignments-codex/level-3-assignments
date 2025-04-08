# Assignment (Week 6, Day 3): Testing Async Functions & Mocking API Calls

## Objective

- Create a **new React project** (Webpack/Babel) with **Jest**.
- Write and test an **asynchronous function** (e.g., a fetch call) using **mocks**.
- Verify that at least **one test** checks the **async result** properly.

## Instructions

### Part 1: Project Setup

1. **Create a New Folder**
   - Example name: `react-jest-async`.
   - Initialize a Node.js project (`npm init -y`).
2. **Install Required Packages**
   - **React & ReactDOM**
   - **Webpack & Babel** (as previously done in Week 3, Day 1)
   - **Jest** & any necessary testing libraries (e.g., `@testing-library/react`, `@testing-library/jest-dom`).
3. **Confirm Build**
   - Ensure you can build and open a minimal React app in the browser before proceeding with tests.

### Part 2: Write an Async Function

1. **Create a Utility or Service File**
   - For instance, define a function that **fetches** data (Any API is fine).
2. **Handle the Response**
   - Return or process the data so you can verify it in tests.

### Part 3: Test with Mocks

1. **Create a Test File**
   - For example, `apiService.test.js`.
2. **Mock the Async Call**
   - Use Jest’s **mock functions** or a mocking library to simulate the fetch/HTTP call.
   - Ensure your test doesn’t rely on an actual network request.
3. **Write a Test**
   - Invoke your function and check that it returns or processes the expected data.
4. **Run Tests**
   - Use `npm test` (or the script defined in your `package.json`) to confirm results.

### Part 4: Push to GitHub

1. **Create a Repository**
   - Name it something like `react-jest-async`.
2. **Include**
   - `webpack.config.js`, Babel config, `package.json`, the service file with the async function, and any test files.

---

## Rubric

| Criteria                        | Limited (0 pts)                                  | Partial (10 pts)                                         | Complete (20 pts)                                                              |
| ------------------------------- | ------------------------------------------------ | -------------------------------------------------------- | ------------------------------------------------------------------------------ |
| **Manual React & Jest Setup**   | Missing/broken config; cannot build or run tests | Partial configuration with some errors                   | Fully configured; React builds, and Jest runs without major issues             |
| **Async Function**              | No function or not asynchronous                  | Async function exists but incomplete or poorly defined   | Clearly defined async function ready to be tested (e.g., fetch-based)          |
| **Mocking & Testing**           | No test or test not mocking the async call       | Test present but mock is incomplete or incorrect         | Test properly mocks the async call; verifies returned data or behavior         |
| **Code Organization & Clarity** | Files missing, unclear naming, or no docs        | Some structure, but insufficient instructions or clarity | Logical structure (e.g., separate test file, service file); clear README       |
| **Overall Functionality**       | Tests fail or do not run at all                  | Tests run sporadically, with partial coverage            | Tests run reliably; the async logic is properly verified (pass/fail scenarios) |
