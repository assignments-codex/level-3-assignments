## Objective

- **Isolating data-access code** in its own file (`dynamo.js`)

- **Reusing** the AWS SDK calls you wrote yesterday

- **Scanning & creating** items in DynamoDB from React

- **Managing AWS credentials** safely with environment variables

- **Running** your project with a single `npm run dev`

---

## Instructions

## 1 Project Setup

1. Scaffold a fresh React project (CRA, Vite, or your manual Webpack/Babel starter from Week 3 Day 1).

2. Run **`npm run dev`** and confirm a blank app appears.

---

## 2 AWS Prerequisites

### 2.1 DynamoDB Table

| Setting      | Value             |
| ------------ | ----------------- |
| Table name   | **`Todo`**        |
| Partition PK | **`id`** (String) |
| Region       | **us-east-1**     |

### 2.2 IAM User + Access Key

1. AWS Console → **IAM → Users → Add user** (e.g., `todo-demo-user`).

2. Attach a policy that allows **`dynamodb:Scan` and `dynamodb:PutItem`** on the `Todo` table (or `AmazonDynamoDBFullAccess`).

3. In the **Security credentials** tab, create an **access key** and copy the **Access key ID** & **Secret access key**.

### 2.3 Local env vars

Create `.env` (or `.env.local`) in project root:

```env
REACT_APP_AWS_REGION=us-east-1
REACT_APP_AWS_ACCESS_KEY_ID=YOUR_KEY_ID
REACT_APP_AWS_SECRET_ACCESS_KEY=YOUR_SECRET_KEY
```

Restart the dev server after saving the file.

---

## 3 Install SDK Packages

```bash
npm install @aws-sdk/client-dynamodb @aws-sdk/lib-dynamodb
```

---

## 4 Build the Helper Module

1. Inside `src/`, add **`dynamo.js`**.

2. In that file:

   - Configure a `DynamoDBClient` with `region` & `credentials` from `process.env`.

   - Wrap it using `DynamoDBDocumentClient.from(client)`.

   - **Export**:

     - `scanTodos()` → returns all items in `Todo`.

     - `createTodo(item)` → writes a new item.

_(No AWS code should remain inside **`App.jsx`**.)_

---

## 5 Wire It Up in `App.jsx`

- `useEffect` → `scanTodos()` on first render, store results in state.

- Simple input + button:

  1. Build `{ id, text, completed:false }`.

  2. Call `createTodo()`.

  3. Append to local state for instant UI feedback.

---

## 6 Verification

| ✅               | How to confirm                                                |
| ---------------- | ------------------------------------------------------------- |
| Env vars loaded  | `console.log(process.env.REACT_APP_AWS_REGION)` → `us-east-1` |
| Scan works       | Items appear in DevTools or on the page at load               |
| Create works     | “Add” writes to DynamoDB **and** updates UI                   |
| Helper isolation | Only `dynamo.js` imports AWS SDK                              |

Take one screenshot of the DynamoDB table with at least one new record and add it to your repo (e.g., `docs/demo.png`).

---

## 7 Submission

Push to GitHub. In `README.md` include:

- Setup & run steps (`npm install`, `npm run dev`)

- Where to place AWS creds

- The screenshot path

Share the repo URL with your instructor.

---

## 8 Rubric (100 pts)

| Category (20 pts each)         | 0 pts                     | 10 pts                                 | 20 pts (full)                            |
| ------------------------------ | ------------------------- | -------------------------------------- | ---------------------------------------- |
| **React Setup & Build**        | App fails to run          | Builds but throws AWS/JS errors        | `npm run dev` launches cleanly           |
| **Helper Module Organization** | All AWS code in `App.jsx` | Mixed placement but functional         | All AWS calls isolated in `dynamo.js`    |
| **Scan Functionality**         | Missing or crashes        | Runs manually / partially              | Auto-scans & displays/logs all items     |
| **Create Functionality**       | Missing or fails          | Writes to DB but UI not updated        | Writes to DB **and** updates UI          |
| **Verification Evidence**      | Screenshot absent / wrong | Screenshot present but unclear/inexact | Clear screenshot showing new table items |
