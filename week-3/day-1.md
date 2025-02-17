# Assignment 1 (Week 3, Day 1): Setting Up React.js with Vite

## Objective

- Learn how to create a React.js project using Vite as a build tool.
- Practice initial project configuration and basic React component structure.
- Gain familiarity with running and bundling a React project quickly.

## Instructions

### Part 1: Initialize a Vite React Project

1. **Create a New Folder**
   - Name it something like `react-vite-setup`.
2. **Set Up with Vite**
   - Use Vite’s recommended method for initializing a React project (for example, the `npm create vite@latest` approach).
3. **Install Dependencies**
   - After the setup, ensure your `package.json` includes React and ReactDOM dependencies.

### Part 2: Explore the Project Structure

4. **Open the Project**
   - Note where the main entry file (e.g., `main.jsx` or `main.js`) is located.
   - Identify the default `App.jsx` (or similarly named) component.
5. **Run the Development Server**
   - Use the appropriate script (often `npm run dev`) to start the local server.
   - Check that you can load your React app in the browser.

### Part 3: Create or Modify a Simple Component

6. **Edit `App.jsx`**
   - Replace or modify the default content with something meaningful (e.g., a heading, a paragraph about what you learned, or a simple button).
7. **Confirm It Works**
   - Reload the app in your browser and ensure your changes are visible.

### Part 4: Build for Production (Optional Check)

8. **Build the Project**
   - Run the build script (typically `npm run build`) to generate a production-ready folder (e.g., `dist`).
9. **Inspect Output**
   - Note how your original files are bundled and optimized for production.

---

## Submission

- **GitHub Repository**
  1. Create a repository named `react-vite-setup`.
  2. Commit and push your entire project, including:
     - `package.json` and `package-lock.json`
     - Any Vite config files
     - The `src` folder (with your React components)
  3. Provide your GitHub repository URL for review.

---

## Rubric

| Criteria                              | Limited (0 pts)                                   | Partial (3 pts)                                              | Complete (5 pts)                                                                     |
| ------------------------------------- | ------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| **1. Project Initialization**         | Did not create or initialize a Vite React project | Project created but with errors or incomplete dependencies   | Project successfully initialized with React and all necessary dependencies installed |
| **2. React Component Usage**          | No custom or modified component created           | Basic component created but incomplete or not rendering      | Clear modification or creation of a React component that renders without errors      |
| **3. Development & Build Scripts**    | Did not run dev server or no build attempted      | Dev server runs, but build process untested or incomplete    | Successfully runs dev server and generates a production build (e.g., `dist` folder)  |
| **4. Code Organization & Clarity**    | Poorly organized files; unclear structure         | Some organization, but minor confusion in folder/file naming | Well-structured project with logical file/folder organization                        |
| **5. Deployment & GitHub Submission** | Repo or link not provided                         | Repo exists but missing required files or incomplete commits | Complete repo with all source files, properly committed and submitted as instructed  |
