### Objective

- Extending a helper module with new DynamoDB operations

- Updating existing items in the Todo table

- Deleting items by id

### Instructions

---

## Instructions

## 1 Project Continuation

Keep working in yesterday’s Day 3 repository (or clone it fresh if you’re behind).
Verify `npm run dev` still starts the app and **scan / create** both work.

---

## 2 Add New Helpers

### 2.1 Open `src/dynamo.js`

1. **Import** `UpdateCommand` and `DeleteCommand` from `@aws-sdk/lib-dynamodb`.

2. **Add & export** two async functions:

`export async function updateTodo(id, updates) { /* … */ } export async function deleteTodo(id) { /* … */ }`

| Function     | Purpose                                                | Sample call                              |
| ------------ | ------------------------------------------------------ | ---------------------------------------- |
| `updateTodo` | Modify fields on a single item (e.g., toggle complete) | `updateTodo("123", { completed: true })` |
| `deleteTodo` | Remove an item entirely                                | `deleteTodo("123")`                      |

> **Hint:** Use `UpdateExpression`, `ExpressionAttributeNames`, and `ExpressionAttributeValues` for `updateTodo`.

_(Still **no** AWS SDK code inside `App.jsx`.)_

---

## 3 Wire Up the UI

### 3.1 Update Handling

- Add a checkbox (or button) beside each todo row.

- On click, call `updateTodo(id, { completed: !current })` and then update local state so the change is reflected instantly.

### 3.2 Delete Handling

- Add a small “×” or “Delete” button next to each item.

- On click, call `deleteTodo(id)` and remove the item from local state.

---

## 4 Verification

| ✅                      | How to confirm                                                         |
| ----------------------- | ---------------------------------------------------------------------- |
| **Update works**        | Toggling a checkbox updates `completed` in DynamoDB and the UI         |
| **Delete works**        | Clicking delete removes the row in DynamoDB and disappears from the UI |
| **Helper isolation**    | Only `dynamo.js` imports AWS SDK                                       |
| **Env vars still load** | No hard-coded keys in source                                           |

Take a new screenshot of the DynamoDB console showing at least one **updated** and one **deleted** item (use the “view deleted” toggle in the AWS console if needed). Add it to your repo (e.g., `docs/demo-day4.png`).

---

## 5 Submission

1. Commit & push all changes.

2. Update `README.md` with a short “Day 4” section describing how to use update/delete.

3. Include the new screenshot path.

4. Share the repo link with your instructor.

---

| Category (20 pts each)         | 0 pts                            | 10 pts                                     | 20 pts (full)                                   |
| ------------------------------ | -------------------------------- | ------------------------------------------ | ----------------------------------------------- |
| **React Build & Scan/Create**  | App fails or old features broken | Old features work but with warnings/errors | Previous features still work flawlessly         |
| **Helper Module Organization** | AWS calls scattered in UI        | Mixed placement but functional             | All AWS calls live only in `dynamo.js`          |
| **Update Functionality**       | Missing or crashes               | Updates DB _or_ UI, not both               | Successfully updates DB **and** UI              |
| **Delete Functionality**       | Missing or crashes               | Deletes in DB _or_ UI, not both            | Successfully deletes in DB **and** removes UI   |
| **Verification Evidence**      | No screenshot / wrong file       | Screenshot present but unclear/incomplete  | Clear screenshot showing updated & deleted rows |
