## Week 4, Day 2: Simple Read & Write in One File

### Objective

Build a single-file React application that uses the AWS SDK to **scan** and **create** items in your DynamoDB `Todo` table.

### Steps

1. **Initialize Project**
   Scaffold a blank React app. Verify it runs without errors.

2. **IAM User Setup**

   - In AWS Console → IAM → Users → Add user.
   - Enter a user name (e.g., `todo-demo-user`) and click **Next**.
   - On the **Permissions** page, attach the **AmazonDynamoDBFullAccess** policy and continue.
   - After creating the user, go to their **Security credentials** tab.
   - Click **Create access key** to generate an **Access key ID** and **Secret access key**—**copy both** now (you won’t see the secret again).

3. **DynamoDB Table** **DynamoDB Table**

   - In AWS Console → DynamoDB → Tables → Create table.
   - Table name: `Todo`
   - Partition key: `id` (String)
   - Create the table.

4. **Environment Variables**

   - In project root, add a `.env` (or `.env.local`) file:

     ```env
     REACT_APP_AWS_REGION=us-east-1
     REACT_APP_AWS_ACCESS_KEY_ID=YOUR_KEY_ID
     REACT_APP_AWS_SECRET_ACCESS_KEY=YOUR_SECRET_KEY
     ```

5. **App.jsx Implementation**

   - Install and import the AWS SDK packages in your React file:

     ```bash
     npm install @aws-sdk/client-dynamodb @aws-sdk/lib-dynamodb
     ```

   - Replace your `src/App.jsx` content with the template below:

   ```jsx
   import React, { useState, useEffect } from "react";
   import { DynamoDBClient } from "@aws-sdk/client-dynamodb";
   import {
     DynamoDBDocumentClient,
     ScanCommand,
     PutCommand,
   } from "@aws-sdk/lib-dynamodb";

   const client = new DynamoDBClient({
     region: process.env.REACT_APP_AWS_REGION,
     credentials: {
       accessKeyId: process.env.REACT_APP_AWS_ACCESS_KEY_ID,
       secretAccessKey: process.env.REACT_APP_AWS_SECRET_ACCESS_KEY,
     },
   });
   const docClient = DynamoDBDocumentClient.from(client);

   async function scanTodos() {
     const { Items } = await docClient.send(
       new ScanCommand({ TableName: "Todo" }),
     );
     return Items || [];
   }

   async function createTodo(item) {
     await docClient.send(new PutCommand({ TableName: "Todo", Item: item }));
   }

   export default function App() {
     const [todos, setTodos] = useState([]);
     const [text, setText] = useState("");

     useEffect(() => {
       scanTodos().then(setTodos);
     }, []);

     const handleAdd = async () => {
       if (!text.trim()) return;
       const newItem = { id: Date.now().toString(), text, completed: false };
       await createTodo(newItem);
       setTodos((prev) => [...prev, newItem]);
       setText("");
     };

     return (
       <div style={{ padding: 20 }}>
         <h1>Todo App</h1>
         <input
           value={text}
           onChange={(e) => setText(e.target.value)}
           placeholder="New todo"
           style={{ marginRight: 8 }}
         />
         <button onClick={handleAdd}>Add</button>

         <ul style={{ marginTop: 16 }}>
           {todos.map((t) => (
             <li key={t.id}>{t.text}</li>
           ))}
         </ul>
       </div>
     );
   }
   ```

6. **Verify**

   - Start your React app.
   - Invoke `scanTodos()` on load and log or display the results in your UI.
   - Use the “Add” button to call `createTodo()` and confirm new items appear in DynamoDB. **Verify**
   - Start your React app.
   - Invoke `scanTodos` on load and log the results.
   - Use `createTodo` to add entries and confirm they appear in DynamoDB.
