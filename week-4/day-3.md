# Assignment (Week 4, Day 3): Reading from DynamoDB in a React App

## Objective

- **Set up a new React project** from scratch with **Webpack and Babel** (see **Week 3, Day 1** for guidance).

- Use **AWS IAM credentials** and the **AWS SDK** to **scan** a DynamoDB table (retrieve all items).

- Log or display the data in the browser console.

## Instructions

### 1. Create Your React Project

Follow your instructor’s usual workflow to scaffold a React app (e.g., `create-react-app`, Vite, or manual Webpack/Babel). Verify that `npm start` (or `npm run dev`) launches your blank React application.

---

### 2. Create the DynamoDB Table

1. In the AWS Management Console, **confirm the region** in the top‑right is set to **US East (N. Virginia) (us-east-1)**.

2. Open **DynamoDB** → **Tables** → **Create table**.

3. Set **Table name** to `Todo`.

4. Under **Partition key**, enter **`id`** and choose **String**.

5. Leave all other settings as default, then click **Create table**.

---

### 3. Install AWS SDK Packages

In your React project directory, run:

```bash
npm install @aws-sdk/client-dynamodb @aws-sdk/lib-dynamodb
```

---

### 4. Create an IAM User for Demo

1. In the AWS Console, go to **IAM** → **Users** → **Add users**.

2. Enter a user name (e.g., `todo-demo-user`).

3. Select **Programmatic access** and proceed.

4. On **Set permissions**, attach the **AmazonDynamoDBFullAccess** policy.

5. Create the user and **copy** the **Access key ID** and **Secret access key** (you’ll only see the secret once).

---

### 5. Configure Environment Variables

In your project root, create a file named `.env.local` (or `.env`):

```env
REACT_APP_AWS_REGION=us-east-1
REACT_APP_AWS_ACCESS_KEY_ID=YOUR_ACCESS_KEY_ID
REACT_APP_AWS_SECRET_ACCESS_KEY=YOUR_SECRET_ACCESS_KEY
```

> Prefix environment variables as `REACT_APP_` (for Create React App) or `VITE_` (for Vite) to have them exposed in `process.env` or `import.meta.env`.

---

### 6. Initialize the DynamoDB Client

Create `src/ddbClient.js`:

```js
import { DynamoDBClient } from "@aws-sdk/client-dynamodb";
import {
  DynamoDBDocumentClient,
  ScanCommand,
  PutCommand,
  UpdateCommand,
  DeleteCommand,
} from "@aws-sdk/lib-dynamodb";

const client = new DynamoDBClient({
  region: process.env.REACT_APP_AWS_REGION,
  credentials: {
    accessKeyId: process.env.REACT_APP_AWS_ACCESS_KEY_ID,
    secretAccessKey: process.env.REACT_APP_AWS_SECRET_ACCESS_KEY,
  },
});

export const ddbClient = DynamoDBDocumentClient.from(client);

export const fetchTodos = () =>
  ddbClient.send(new ScanCommand({ TableName: "Todo" }));

export const addTodo = (item) =>
  ddbClient.send(new PutCommand({ TableName: "Todo", Item: item }));

export const updateTodo = (id, completed) =>
  ddbClient.send(
    new UpdateCommand({
      TableName: "Todo",
      Key: { id },
      UpdateExpression: "SET completed = :c",
      ExpressionAttributeValues: { ":c": completed },
    }),
  );

export const deleteTodo = (id) =>
  ddbClient.send(new DeleteCommand({ TableName: "Todo", Key: { id } }));
```

---

### 7. Build the React UI

Replace your main component (e.g., `src/App.jsx`) with:

```jsx
import React, { useState, useEffect } from "react";
import { fetchTodos, addTodo, updateTodo, deleteTodo } from "./ddbClient";

export default function App() {
  const [todos, setTodos] = useState([]);
  const [text, setText] = useState("");

  useEffect(() => {
    fetchTodos().then(({ Items }) => setTodos(Items));
  }, []);

  const handleAdd = async () => {
    if (!text.trim()) return;
    const newItem = { id: Date.now().toString(), text, completed: false };
    await addTodo(newItem);
    setTodos((prev) => [...prev, newItem]);
    setText("");
  };

  const handleToggle = async (id, comp) => {
    await updateTodo(id, !comp);
    setTodos((prev) =>
      prev.map((t) => (t.id === id ? { ...t, completed: !comp } : t)),
    );
  };

  const handleDelete = async (id) => {
    await deleteTodo(id);
    setTodos((prev) => prev.filter((t) => t.id !== id));
  };

  return (
    <div style={{ padding: 20 }}>
      <h1>React + DynamoDB TODO</h1>
      <input
        value={text}
        onChange={(e) => setText(e.target.value)}
        placeholder="New task"
        style={{ marginRight: 8 }}
      />
      <button onClick={handleAdd}>Add</button>
      <ul style={{ marginTop: 16 }}>
        {todos.map(({ id, text, completed }) => (
          <li
            key={id}
            style={{ marginBottom: 8 }}
          >
            <label
              style={{ textDecoration: completed ? "line-through" : "none" }}
            >
              <input
                type="checkbox"
                checked={completed}
                onChange={() => handleToggle(id, completed)}
              />{" "}
              {text}
            </label>
            <button
              onClick={() => handleDelete(id)}
              style={{ marginLeft: 12 }}
            >
              Delete
            </button>
          </li>
        ))}
      </ul>
    </div>
  );
}
```

---

### 8. Run & Verify

1. Launch your app (`npm start` or `npm run dev`).

2. Open the React app in a browser.

3. Add, toggle, and delete items—watch changes appear in your DynamoDB table.

---

### Submission & Rubric

- **GitHub Repo**: Include your project with a `README` covering setup, table creation, and how to run.

- **Functionality**: App must scan items on load and support add/toggle/delete seamlessly.

- **AWS Setup**: Correct table creation, correct IAM permissions, and correct env configuration.

| Criteria                | 0 pts                        | 10 pts                    | 20 pts                              |
| ----------------------- | ---------------------------- | ------------------------- | ----------------------------------- |
| **React Setup**         | Does not build or run        | Builds but errors persist | Clean setup per instructor workflow |
| **DynamoDB Table**      | Not created or misconfigured | Created but wrong schema  | `Todo` table with `id` String PK    |
| **AWS SDK Integration** | Missing or broken code       | Partial functionality     | Fully scans, adds, updates, deletes |
| **Code Organization**   | Monolithic and unclear       | Some separation but messy | `ddbClient.js` + clear UI code      |
|                         |                              |                           |                                     |
