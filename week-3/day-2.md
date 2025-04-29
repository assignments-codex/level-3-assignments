### Objective

Use **`useState`** and **props** to build a tiny CRUD-style feature: add pets with a form and list them on the page.

### Setup

1. **Create a fresh project**

   `npx react-webpack-codex pet-adoption && cd pet-adoption && code .`

2. **Clean the scaffold**

   - Empty / delete starter CSS in `style.css`.

   - Remove default component code in `App.jsx`, `index.jsx`, and any sample components.

---

### Required Files (inside `src/`)

| File          | Purpose                                                                 |
| ------------- | ----------------------------------------------------------------------- |
| `App.jsx`     | Root component; owns **array of pets** state.                           |
| `PetForm.jsx` | Form component; collects **name, species, age** and passes data upward. |
| `PetCard.jsx` | Presentational card; displays a single pet’s info.                      |

---

### Functional Requirements

1. **App.jsx**

   - Initialize `pets` state (empty array).

   - Provide a callback prop to `<PetForm />` that **adds** a new pet (use an immutable update).

   - Render a list of `<PetCard />` components by mapping over `pets`.

2. **PetForm.jsx**

   - Manage three controlled inputs (`name`, `species`, `age`) with `useState`.

   - On submit, bundle input values into an object `{ id, name, species, age }` and call the callback from props.

   - Clear inputs after submission.

3. **PetCard.jsx**

   - Receive a `pet` prop and display its `name`, `species`, and `age`.

> **Hook & Component Rules**
>
> - Call hooks **only at the top level** of React functions.
>
> - **Do not** mutate state directly; create new arrays/objects.
>
> - Component names start with a **capital letter**.

---

### Styling Guidelines

- Keep styles simple; add only what you can type live in class.

- Suggested: centered layout, subtle card borders/shadows, basic form spacing.

---
