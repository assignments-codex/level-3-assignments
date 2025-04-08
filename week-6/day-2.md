# Task (Week 6, Day 2): Writing a Basic Test for a React Component

## Objective

- Build on your **Day 1 Jest setup** by creating a **simple unit test** for a React component.
- Practice using **@testing-library/react** to **render** a component and **assert** expected behavior.

## Instructions

1. **Confirm Your Jest Setup**

   - Continue from your Day 1 project (or replicate the same Jest configuration).
   - Make sure `npm test` runs without errors.

2. **Create a React Component to Test**

   - You can use a minimal example (e.g., a `<Button>` or `<Greeting>` component).
   - Keep the logic simple, such as displaying some text or accepting a prop to show.

3. **Write a Test File** (e.g., `Greeting.test.js`)

   - Import:
     - **React** (if needed)
     - **render** and **screen** from `@testing-library/react`
     - The component you want to test.
   - For example:

     ```js
     import { render, screen } from "@testing-library/react";
     import Greeting from "../Greeting";

     test("renders the greeting text", () => {
       render(<Greeting />);
       const textElement = screen.getByText(/hello world/i);
       expect(textElement).toBeInTheDocument();
     });
     ```

4. **Run Your Test**

   - Use `npm test` (or the test script you configured in your `package.json`).
   - Verify the test **passes**.

5. **Experiment Further**
   - Add a **button** and test a **click event**.
   - Pass a **prop** to your component and test the rendered output changes.

---

## Submission

- This is a **practice task**, so **no formal submission** is required.
- If you wish, commit your changes to your **Day 1** repository or create a new branch to track your progress.
