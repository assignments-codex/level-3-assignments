# Assignment (Week 4, Day 3): Reading from DynamoDB in a React App

## Objective

- **Set up a new React project** from scratch with **Webpack and Babel** (see **Week 3, Day 1** for guidance).

- Use **AWS IAM credentials** and the **AWS SDK** to **scan** a DynamoDB table (retrieve all items).

- Log or display the data in the browser console.

## Instructions

### Part 1: Project Setup with Webpack & Babel

1. **Create a New Folder**

   - Name it something like `dynamodb-react-read`.

   - Initialize it (e.g., `npm init -y`), install and configure **Webpack** and **Babel** as you did in **Week 3, Day 1**.

2. **Add React**

   - Install `react` and `react-dom`.

   - Confirm your basic React setup is working by building (`npm run build`) and opening the resulting HTML page in a browser.

### Part 2: AWS SDK and .env Configuration

1. **Install AWS SDK**

   ```bash
   npm install aws-sdk
   ```

2. **Use a .env File**

   - Store your **AWS_ACCESS_KEY_ID** and **AWS_SECRET_ACCESS_KEY** in a local `.env` file to keep them out of your code.

   - Ensure you don’t push your real credentials to GitHub.

### Part 3: Scanning Your DynamoDB Table

1. **Create a JS Module for AWS**

   - In a file (e.g., `awsDynamo.js`), configure the AWS SDK with:

     - Your **region**

     - **Credentials** (loaded from `.env` or a config object)

   - Use **`documentClient.scan`** to retrieve **all items** from the table you seeded on Day 2.

     - `scan` is simplest when you want everything in a small table.

2. **Invoke the Function from Your React Code**

   - In your main React component or a small script, call your `scan` function when the page loads.

   - **Console.log** the returned data to confirm it’s retrieving items from DynamoDB.

### Part 4: Verify & Submit

1. **Build and Open**

   - Run your build, open the app in a browser, and check the console for your table data.

2. **Troubleshoot**

   - If you see permission errors, revisit your IAM policy to ensure `dynamodb:Scan` is allowed.

---

## Submission

- **GitHub Repository**:

  - Push this project to a new repository.

  - Include a short **README** with steps to install, build, and run, along with a note about where to see the logged data (browser console).

---

## Rubric

| Criteria                        | Limited (0 pts)                                 | Partial (10 pts)                                          | Complete (20 pts)                                                        |
| ------------------------------- | ----------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------ |
| **Webpack/Babel React Setup**   | Incorrect or missing setup; app won’t build/run | Partially working setup with errors or incomplete         | Fully working manual setup following Week 3, Day 1 pattern               |
| **IAM Permissions**             | No valid read permission; DynamoDB scan fails   | Permissions partially correct, data load inconsistent     | Correctly configured `dynamodb:Scan` permission; data loads reliably     |
| **AWS SDK Integration**         | AWS not installed or improperly configured      | SDK installed but code not fully functional               | AWS SDK correctly configured; able to connect to DynamoDB                |
| **Data Retrieval**              | No data retrieved or constant errors            | Some data retrieval but with errors or incomplete results | Successfully retrieves items from DynamoDB and logs them                 |
| **Code Organization & Clarity** | Code is overly cluttered or unclear             | Some organization, but not fully clear                    | Logical, minimal structure (separate AWS config file, simple React code) |
