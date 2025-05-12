# Assignment (Week 5, Day 1): Introduction to SASS with Nesting and Variables

## Objective

1. Set up a **new React project** using **Webpack** and **Babel**.

2. Configure **SASS** compilation and demonstrate **nesting** plus **variables** in `.scss` files.

## Instructions

### Part 1: Initial Project Setup

## Objective

- Build a single-file React application that uses the AWS SDK to scan and create items in your DynamoDB Todo table.

### Instructions

1. **Create a new React project**
   Use the workflow or CLI your instructor recommends. Confirm it runs locally before you begin styling.

2. **Convert CSS to SCSS**
   Rename your existing `.css` file(s) to `.scss` and ensure your build pipeline processes SCSS without errors.

3. **Define a color theme**
   In your main stylesheet, declare **five** SCSS variables for your palette (e.g. primary, secondary, accent, muted, highlight). Tools like coolors.co can help you pick values.

4. **Demonstrate nesting**
   Still in that stylesheet, create **three** container classes (e.g. `.section-one`, `.section-two`, `.section-three`). Inside each, nest element selectors (headings, links, buttons, etc.) to show SCSS’s nesting syntax.

5. **Deploy to Netlify**
   Push your code to GitHub, connect the repo in Netlify, and deploy. Verify your live site reflects your SCSS styles.

---

**Submission**

- **GitHub Repo URL**

- **Live Site URL** (Netlify)

> Both links are required.

---

**Rubric (100 points)**

| Criteria                     | Limited (0 pts)                        | Partial (10 pts)                                 | Complete (20 pts)                                              |
| ---------------------------- | -------------------------------------- | ------------------------------------------------ | -------------------------------------------------------------- |
| **Project setup & run**      | Doesn’t start or build                 | Builds/runs with errors or warnings              | Builds and runs cleanly via prescribed workflow                |
| **SCSS conversion & config** | SCSS not processed or build breaks     | `.scss` compiles but with issues                 | SCSS integrates smoothly; build pipeline error-free            |
| **Color theme variables**    | Fewer than 5 variables or poor naming  | 5 variables defined but inconsistent theme       | Five well-named variables; cohesive color palette              |
| **Nesting demonstration**    | No nesting or incorrect nesting syntax | Some nesting shown but not in all three sections | Clear, correct nesting in all three container classes          |
| **Deployment & submission**  | No live link or no repo link           | One link missing or deploy fails                 | Both GitHub and live URLs provided; site loads with new styles |
