# Assignment (Week 6, Day 1): Setting Up Vitest for React Testing

## Objective

- Create a **new React project** and set up **Vitest** for testing.
- Configure **basic test scripts** in `package.json`.
- Verify Vitest runs a simple test successfully.

## Instructions

### Part 1 – New React Project Setup

1. **Create a new React project**

   ```bash
   npm create vite@latest
   ```

   - Select **React**.
   - Select **JavaScript** (or **TypeScript** if preferred).

2. **Install dependencies**

   ```bash
   cd your-project-name
   npm install
   ```

3. **Verify your project works**

   ```bash
   npm run dev
   ```

   - Ensure your React app loads successfully in the browser.

---

### Part 2 – Install & Configure Vitest

1. **Install testing dependencies**

   ```bash
   npm install --save-dev vitest @testing-library/react @testing-library/jest-dom jsdom
   ```

2. **Configure Vitest**

   Update your existing `vite.config.js`:

   ```js
   import { defineConfig } from "vite";
   import react from "@vitejs/plugin-react";

   export default defineConfig({
     plugins: [react()],
     test: {
       environment: "jsdom",
       globals: true,
     },
   });
   ```

3. **Update your scripts**

   In `package.json` add a test script:

   ```json
   "scripts": {
     "dev": "vite",
     "build": "vite build",
     "preview": "vite preview",
     "test": "vitest"
   }
   ```

---

### Part 3 – Write a Simple Test

1. **Create a test file**

   - Place it beside your component in `src` (e.g., `src/App.test.jsx`).

2. **Write your first test**

   ```jsx
   import { render, screen } from "@testing-library/react";
   import "@testing-library/jest-dom";
   import App from "./App";

   test("renders hello message", () => {
     render(<App />);
     expect(screen.getByText(/vite \+ react/i)).toBeInTheDocument();
   });
   ```

---

### Part 4 – Run Your Tests

```bash
npm test
```

- Confirm that Vitest successfully runs your test.
- Passing tests display clearly in the terminal.

---

## Submission

- **GitHub Repository**

  - Push your complete project (source files, configs, tests).
  - Include a **README** with clear instructions (`npm install`, `npm run dev`, `npm test`).

---

## Rubric

| Criteria                              | Limited (0 pts)                   | Partial (13 pts)                       | Complete (25 pts)                                                |
| ------------------------------------- | --------------------------------- | -------------------------------------- | ---------------------------------------------------------------- |
| **React + Vite Setup**                | Build broken or missing key files | Project builds but incomplete setup    | React + Vite project fully working                               |
| **Vitest Installation & Config**      | Missing Vitest or scripts         | Vitest installed, configuration issues | Vitest fully configured, `npm test` runs successfully            |
| **Basic Test Implementation**         | No test file or test never runs   | Test file present but incorrect/fails  | At least one passing test displayed clearly in terminal          |
| **Code Organization & Documentation** | Unorganized, unclear README       | Basic organization, incomplete README  | Clear organization, helpful README (install, run, test commands) |
