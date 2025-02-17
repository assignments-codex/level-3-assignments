# Assignment 3 (Week 3, Day 5): Deploying the Weather App & React Review

## Objective

- Finalize your multi-day or single-day weather app.
- Practice **deploying** a React application to **Netlify**.
- Review core React concepts: component structure, state management, and data fetching.

## Instructions

### Part 1: Finalize Your Weather App

1. **Polish the UI**
   - Tidy up layout and design if needed (optional).
   - Ensure your app clearly displays weather data without errors.
2. **Review Component Architecture**
   - Confirm your components are logically organized.
   - Make sure any hooks (`useState`, `useEffect`, etc.) are used correctly.

### Part 2: Prepare for Deployment

1. **Build the App**
   - Run your build script (e.g., `npm run build` if using Vite or Create React App).
   - Verify a production-ready folder (commonly `dist` or `build`) is generated.
2. **Check for Environment Variables** (If Applicable)
   - If your weather API requires a key, ensure you manage it securely (e.g., `.env` file).
   - Know how you’ll handle these in Netlify (if needed).

### Part 3: Deploy to Netlify

1. **Sign Up / Log In**
   - If you don’t have a Netlify account, create one (free tier available).
2. **Connect Your Repository**
   - On Netlify, create a **New Site** and link it to your GitHub repo.
   - Or drag-and-drop your build folder directly if you’re not using repo auto-deploy.
3. **Verify Deployment**
   - Wait for the build process to finish.
   - Test your **Netlify URL** in the browser to ensure your weather app runs as expected.

### Part 4: Reflect on React Basics

- **Take a moment** to revisit:
  - How state and effects work (`useState`, `useEffect`).
  - How data is passed between components (props).
  - Any complexities you encountered with data fetching, error handling, or conditional rendering.

---

## Submission

4. **GitHub Repository**
   - Push your final code to a repository named `react-weather-deployment` (or use your existing weather app repo).
5. **Netlify Live URL**
   - Provide the public URL from Netlify that renders your deployed weather app.
6. **Submission Link**
   - Turn in the GitHub repo link and the Netlify live URL as your final submission.

---

## Rubric

| Criteria                               | Limited (0 pts)                                  | Partial (3 pts)                                                   | Complete (5 pts)                                                                   |
| -------------------------------------- | ------------------------------------------------ | ----------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **1. Finalized Weather Features**      | App is incomplete or data display is broken      | Basic weather data shown, but partial or with errors              | Fully functional single/multi-day weather display with no major bugs               |
| **2. React Concepts Review**           | Little evidence of applying React best practices | Some React concepts used, but organization or state usage unclear | Components are well-structured; correct usage of hooks, props, and component logic |
| **3. Code Organization & Readability** | Code is disorganized or difficult to follow      | Moderately structured but needs more clarity                      | Logical file/folder setup; clear naming, minimal or no console warnings            |
| **4. Build Process**                   | No build completed or build errors persist       | Build process set up but partially failing                        | Successful build with all assets properly packaged                                 |
| **5. Netlify Deployment & Submission** | No deployment link provided or link is broken    | Deployed but with errors, or incomplete link provided             | Working Netlify URL submitted; repo is up-to-date and accessible                   |
