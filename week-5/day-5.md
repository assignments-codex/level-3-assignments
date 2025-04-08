# Assignment (Week 5, Day 5): Comprehensive Styling Review in React

## Objective

- **Create a new React project** (manual Webpack/Babel) showcasing the styling techniques from this week:
  - **SASS** (nesting, variables)
  - **Basic animations**
  - **Component library**
  - **Responsive design**

## Instructions

### Part 1: Project Setup

1. **Create a New Folder**
   - For instance, `react-styling-review`.
   - Initialize a Node.js project (`npm init -y`) and configure **Webpack**, **Babel**, **React**, and **SASS**—just as you did in earlier Week 5 assignments.

### Part 2: Integrate Styling Techniques

1. **SASS**
   - Use **nesting** (e.g., `.parent { .child { ... } }`) and at least one **variable** (e.g., `$primary-color: #3498db;`).
2. **Animations**
   - Add a simple **slide**, **fade**, or **hover** effect.
   - You can do this via **CSS/SASS** animations or an **animation library** (like Framer Motion).
3. **Component Library**
   - Install at least **one** React component library (e.g., **React-Bootstrap** or **Material UI**).
   - Use **one** or **two** components (such as a Navbar, Card, or Button) from that library.
4. **Responsive Layout**
   - Ensure your layout adjusts for mobile, tablet, and desktop.
   - This may involve **media queries** (in SASS) or the layout/grid system in your chosen component library.

### Part 3: Verify & Finalize

1. **Build and Open**
   - Run your Webpack build (e.g., `npx webpack`) and open the resulting **HTML** file in a browser.
2. **Check for Errors**
   - Make sure the console is free of animation or library-related errors.
3. **Polish**
   - Tweak any design inconsistencies (e.g., mismatched colors) to present a cohesive style.

---

## Submission

- **GitHub Repository**
  - Name your new repo (e.g., `react-styling-review`).
  - Include **webpack.config.js**, **.babelrc**, **.scss** files, and all **React** files.
  - Provide a **README** describing how to install, build, and run the project, plus a quick summary of the styling libraries or methods used.

---

## Rubric

| Criteria                          | Limited (0 pts)                                | Partial (10 pts)                                   | Complete (20 pts)                                                              |
| --------------------------------- | ---------------------------------------------- | -------------------------------------------------- | ------------------------------------------------------------------------------ |
| **SASS Usage**                    | No SASS usage or code fails to compile         | SASS present but minimal nesting/variables         | Clear, effective use of SASS (variables, nesting) throughout the project       |
| **Animations**                    | No visible animations or broken implementation | Basic animation attempted but errors or incomplete | Smooth animation(s) integrated (CSS-based or library-based), no major issues   |
| **Component Library Integration** | Not used or improperly installed               | Library used but minimal or partially broken use   | At least one library component used effectively and styled consistently        |
| **Responsive Design**             | Layout breaks on smaller or larger screens     | Partially responsive with some layout issues       | Fully responsive across mobile, tablet, and desktop breakpoints                |
| **Code Organization & Clarity**   | Disorganized files, unclear instructions       | Some structure, but incomplete or unclear README   | Logical folder organization; clear README detailing setup, usage, and features |
