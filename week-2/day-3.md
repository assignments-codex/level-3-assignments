# Assignment 2 (Week 2, Day 3): Tree Shaking & Loaders in Webpack

## Objective

- Demonstrate Webpack’s **tree shaking** feature to remove unused code.
- Practice using **loaders** to handle file types (e.g., CSS, images, or other assets).
- Strengthen understanding of Webpack’s configuration options and how they affect final bundles.

## Instructions

### Part 1: Tree Shaking Essentials

1. **Project Setup**
   - Ensure you have a `webpack.config.js` and at least one JavaScript entry file.
2. **Add Unused Code**
   - Within one of your modules, export multiple functions or variables, but only import and use one or two of them in your main entry file.
   - Example (conceptually):
     - A module that exports `functionA`, `functionB`, and `functionC`, but your main entry only calls `functionA`.
3. **Enable Tree Shaking**
   - Make sure **`mode` is set to `'production'`** in your webpack config.
   - Build your project and confirm that unused exports don’t appear in the final bundle (e.g., check file size or bundle contents).

### Part 2: Introduce a Loader

4. **Choose a Loader**
   - Common examples:
     - **CSS Loader**: For importing CSS files in your JS.
     - **File Loader** or **Asset Modules**: For handling images or fonts.
   - Install the necessary loader package(s) and note them in `devDependencies`.
5. **Configure Your Loader**
   - In your webpack config, add a **module rule** for the file type you want to handle (CSS, images, etc.).
   - For instance, if you’re using the CSS loader, you might add a rule that matches `\.css$` files.
6. **Test the Loader**
   - Import a small CSS file or an image in your JS code.
   - Build the project again and confirm the loader is functioning (e.g., your CSS is applied, or your image is handled in the bundle).

### Part 3: Document Your Observations

- **Tree Shaking**: Make a note of any differences in bundle size or code content when toggling from development to production mode.
- **Loader Behavior**: Summarize how you configured the loader and what it enabled you to do (e.g., how did you import the file, and how did you confirm it worked?).

---

## Submission

7. **Create or Update a GitHub Repository** named something like `webpack-tree-shaking`.
8. **Commit and Push**:
   - Your webpack config file (showing tree shaking and loader configuration).
   - Any relevant source files demonstrating unused exports and the loader usage.
9. **Share the GitHub Repository Link** as your submission.

---

## Rubric

| Criteria                               | Limited (0 pts)                                          | Partial (3 pts)                                                         | Complete (5 pts)                                                                           |
| -------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| **Tree Shaking Implementation**        | No attempt made or unused code remains in final bundle   | Partial success but some unused code may still be included              | Successfully enables tree shaking; unused exports are removed in production builds         |
| **Loader Configuration**               | No loader configured or configuration is incorrect       | Loader partially configured but not fully working                       | Loader properly configured and functioning as expected (CSS, images, or another file type) |
| **Project Structure & Webpack Config** | Lacks a clear structure or config leads to errors        | Structure and config exist but require manual fixes or produce warnings | Organized project folder; a clean Webpack config with minimal or no build warnings         |
| **Code Quality & Documentation**       | Code is disorganized or no written observations included | Some notes provided, but incomplete or unclear                          | Code is well-structured, and observations about tree shaking and loader behavior are clear |
