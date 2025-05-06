## Today’s Task: Read & Write Directly in App.jsx (Week 4, Day 2)

Building on yesterday’s AWS and React setup, today you’ll implement basic **read** and **write** operations to your DynamoDB table entirely within `App.jsx`. Keep it single-file and simple—no extras.

### Objectives

- Fetch all TODO items from DynamoDB on component mount.
- Allow adding a new TODO by writing an item to DynamoDB.
- Use the AWS SDK for JavaScript v3 (`@aws-sdk/client-dynamodb` & `@aws-sdk/lib-dynamodb`).

> **Note:** You already created your IAM user and DynamoDB table (`Todo` with String PK `id`) and set up your `.env` yesterday.

---

### 1. Install AWS SDK (if not already)

```bash
npm install @aws-sdk/client-dynamodb @aws-sdk/lib-dynamodb
```

### 2. Update `src/App.jsx`

Replace your existing component with a version that:

1. Reads all items using **ScanCommand** in a `useEffect` hook.
2. Adds a new item via **PutCommand** in your add-handler.

_No additional files or folders required—keep everything in `App.jsx`._

---

### 3. Run & Verify

1. Start your React app (`npm start` or `npm run dev`).
2. Confirm the AWS Console’s region (top-right) is set to **us-east-1**.
3. Add a few tasks; verify they appear both in the app and in the DynamoDB table.

### 4. Reflection

In a short note, describe:

- What changed compared to yesterday’s multi-file setup?
- One insight you gained about scanning or writing items directly from React.

---

## Week 4, Day 3 Assignment: Reading from DynamoDB in a React App

### Objective

- **Set up a new React project** from scratch with **Webpack and Babel** (refer to Week 3, Day 1).
- Use **AWS IAM credentials** and the **AWS SDK** to **scan** a DynamoDB table and retrieve all items.
- Log or display the retrieved data in the browser console.

### Instructions

1. **Create Your React Project**
   Scaffold a fresh React app using your instructor’s preferred workflow (CRA, Vite, or manual Webpack/Babel). Verify that you can launch a blank app.

2. **Create the DynamoDB Table**

   - In the AWS Console, ensure the region (top-right) is **US East (N. Virginia) (us-east-1)**.
   - Navigate to **DynamoDB → Tables → Create table**.
   - Name it `Todo` with a **String** partition key named `id`.
   - Leave defaults and create.

3. **Install AWS SDK Packages**
   In your project directory, install:

   ```bash
   npm install @aws-sdk/client-dynamodb @aws-sdk/lib-dynamodb
   ```

4. **Create an IAM User for Demo**

   - In AWS Console under **IAM → Users → Add users**, create a user (e.g., `todo-readonly`).
   - Grant **Programmatic access**.
   - Attach a policy that allows **dynamodb\:Scan** on the `Todo` table (you may use `AmazonDynamoDBReadOnlyAccess`).
   - Copy the **Access key ID** and **Secret access key**.

5. **Configure Environment Variables**
   In the project root, make a `.env` (or `.env.local`) file:

   ```env
   REACT_APP_AWS_REGION=us-east-1
   REACT_APP_AWS_ACCESS_KEY_ID=YOUR_KEY_ID
   REACT_APP_AWS_SECRET_ACCESS_KEY=YOUR_SECRET
   ```

6. **Scan the Table**

   - In your main component, import the AWS SDK’s `DynamoDBClient` and `ScanCommand` (from `@aws-sdk/client-dynamodb` and `@aws-sdk/lib-dynamodb`).
   - On component mount, issue a `ScanCommand` against your `Todo` table.
   - Log the returned items to the console (or render them in a simple list).

7. **Verify**

   - Run the app and open DevTools.
   - Ensure scanning succeeds and you see the table items logged.
   - **Capture a screenshot** of the DynamoDB console showing your `Todo` table and its items. Include this screenshot in your README or submission.

---

### Submission & Rubric

- **GitHub Repo**: Push your project with a `README` summarizing setup steps and how to run.
- **Functionality**: Must scan items on load and log/display them.
- **AWS Setup**: Correct table creation and IAM policy for read access.

| Criteria                     | 0 pts                       | 10 pts                         | 20 pts                                 |
| ---------------------------- | --------------------------- | ------------------------------ | -------------------------------------- |
| **React Setup**              | Fails to build or launch    | Builds but missing scan        | Clean project setup & scan works       |
| **DynamoDB Table**           | Not created or wrong schema | Table exists but misconfigured | `Todo` table with `id` String PK       |
| **Scan Functionality**       | No scan or errors           | Partial results or errors      | Successfully scans & logs items        |
| **Code Organization**        | Chaotic or unclear          | Functional but messy           | Single-component clarity               |
| **Verification Screenshots** | None provided               | Provided but unclear           | Provided and clearly shows table items |
