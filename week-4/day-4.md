# Assignment (Week 4, Day 4): Writing and Reading from DynamoDB in a React App

## Objective

- **Create a new React app** (manual Webpack/Babel setup) with proper **IAM** permissions.

- **Write data** to a DynamoDB table from a simple **form** in React.

- **Read and display** items from the same DynamoDB table in the app’s DOM.

## Instructions

### Part 1: Project Setup

1. **Create a New Folder**

   - Name it, for example, `dynamodb-react-crud`.

   - Initialize it (`npm init -y`), and set up **Webpack** and **Babel** based on the pattern from **Week 3, Day 1** (and reinforced in Week 4, Day 3).

2. **Add React**

   - Install `react` and `react-dom`.

   - Verify your setup by running the build and ensuring a basic React component renders.

### Part 2: AWS SDK & Permissions

1. **Install AWS SDK**

   `npm install aws-sdk`

2. **Check IAM Policy**

   - Make sure the IAM credentials you use have:

     - **Write** permissions (e.g., `dynamodb:PutItem`) for adding data.

     - **Read** permissions (e.g., `dynamodb:Scan` or `dynamodb:GetItem`) for retrieving data.

### Part 3: Form to Write Data to DynamoDB

1. **Create a Simple Form**

   - Add fields (for example, a name and a description).

   - On submit, call a function that uses the AWS SDK to **put** or **update** items in your DynamoDB table.

2. **Validate Input** (Optional)

   - Ensure your code handles empty inputs or repeated submissions gracefully.

### Part 4: Read and Display DynamoDB Items

1. **Retrieve Items**

   - In the same project, implement a method to **scan** or **get** items from the table.

2. **Render Items**

   - Show the retrieved items in a basic list or table in your React component.

   - Confirm the newly added items (via your form) appear after refreshing or re-fetching.

---

## Submission

- **GitHub Repository**:

  - Push this project to a new repository (e.g., `dynamodb-react-crud`).

  - Include a **README** describing how to install dependencies, build the app, and run it locally (e.g., `npm install`, `npm run build`, then open your `index.html`).

---

## Rubric

| Criteria                             | Limited (0 pts)                                    | Partial (10 pts)                                           | Complete (20 pts)                                                       |
| ------------------------------------ | -------------------------------------------------- | ---------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Manual Webpack/Babel React Setup** | Setup is broken or incomplete; app won’t build/run | Partially working setup with some errors                   | Fully working, as established in previous assignments                   |
| **IAM Permissions**                  | Missing or incorrect; write/read attempts fail     | Partially correct, can write but not read or vice versa    | Correctly configured for both read and write in DynamoDB                |
| **Form & Write Operation**           | No functional form or DynamoDB write operation     | Form exists but write logic fails or is incomplete         | Form input is successfully saved to DynamoDB                            |
| **Read & Display Data**              | DynamoDB items are not retrieved or displayed      | Retrieval logic is present but buggy or incomplete display | Data is reliably fetched and rendered, including new items              |
| **Code Organization & Clarity**      | Disorganized structure or missing key files        | Some structure, but still unclear how everything fits      | Clear separation of concerns: AWS config, form component, display logic |
