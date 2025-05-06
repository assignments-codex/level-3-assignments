### Objective

- Fetch all TODO items from DynamoDB on component mount.

- Allow adding a new TODO by writing an item to DynamoDB.

- Use the AWS SDK for JavaScript v3 (`@aws-sdk/client-dynamodb` & `@aws-sdk/lib-dynamodb`).

### Instructions

---

### 1. Install AWS SDK (if not already)

```bash
npm install @aws-sdk/client-dynamodb @aws-sdk/lib-dynamodb
```

### 2. Update `src/App.jsx`

Replace your existing component with the code below. It:

1. Reads all items via a **ScanCommand** in `useEffect`.

2. Adds a new item via **PutCommand** in `handleAdd`.

```jsx
import React, { useState, useEffect } from "react";
import { DynamoDBClient } from "@aws-sdk/client-dynamodb";
import {
  DynamoDBDocumentClient,
  ScanCommand,
  PutCommand,
} from "@aws-sdk/lib-dynamodb";

// Initialize DynamoDB client with env vars
const ddb = new DynamoDBClient({
  region: process.env.REACT_APP_AWS_REGION,
  credentials: {
    accessKeyId: process.env.REACT_APP_AWS_ACCESS_KEY_ID,
    secretAccessKey: process.env.REACT_APP_AWS_SECRET_ACCESS_KEY,
  },
});
const docClient = DynamoDBDocumentClient.from(ddb);

export default function App() {
  const [todos, setTodos] = useState([]);
  const [text, setText] = useState("");

  // 1. Read all items on mount
  useEffect(() => {
    async function fetchData() {
      const { Items } = await docClient.send(
        new ScanCommand({ TableName: "Todo" }),
      );
      setTodos(Items || []);
    }
    fetchData();
  }, []);

  // 2. Write a new item
  const handleAdd = async () => {
    if (!text.trim()) return;
    const newItem = { id: Date.now().toString(), text, completed: false };
    await docClient.send(new PutCommand({ TableName: "Todo", Item: newItem }));
    setTodos((prev) => [...prev, newItem]);
    setText("");
  };

  return (
    <div style={{ padding: 16 }}>
      <h1>Simple TODO (Read & Write in App.jsx)</h1>
      <input
        value={text}
        onChange={(e) => setText(e.target.value)}
        placeholder="New task"
        style={{ marginRight: 8 }}
      />
      <button onClick={handleAdd}>Add</button>

      <ul style={{ marginTop: 16 }}>
        {todos.map(({ id, text }) => (
          <li key={id}>{text}</li>
        ))}
      </ul>
    </div>
  );
}
```

---

### 3. Run & Verify

1. Start your React app (`npm start` or `npm run dev`).

2. Ensure your region (top-right AWS Console) is **us-east-1**.

3. Add a few tasks; confirm they appear in the list and in the DynamoDB table.
