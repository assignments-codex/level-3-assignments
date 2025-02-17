# Task (Week 2, Day 2): Exploring Webpack Defaults & Folder Structure

## Objective

- Understand how Webpack behaves with minimal configuration.
- Experiment with different folder structures and config file names.
- Practice reading Webpack documentation to guide your setup decisions.

## Instructions

### Part 1: Minimal Webpack Setup

1. **Create or Reuse a Webpack Project**
   - Option A: Use the **existing** `webpack-intro` project from Day 1.
   - Option B: Create a new folder and run `npm init -y`, then install `webpack` and `webpack-cli` as dev dependencies.
2. **Test Default Behavior**
   - Try running `npx webpack` (or `npm run build` if you created a script) **without** a `webpack.config.js` file and note what happens.
   - Observe how Webpack chooses a default entry and output location if you do **not** specify them.

### Part 2: Custom Folder Structures

1. **Reorganize Your Files**
   - Create a subfolder (e.g., `assets` or `client`) and move your JavaScript files there.
   - See how Webpack reacts with the new structure.
   - You can either rename or move your existing `src` folder, or experiment with an entirely new folder structure.
2. **Adjust Webpack Config (If Needed)**
   - If you add a `webpack.config.js` file, customize your `entry` and `output` paths to match your new folder structure.
   - Observe how different setups (with and without a config file) affect the final bundled output.

### Part 3: Alternative Config File Name (Optional)

1. **Rename `webpack.config.js`**
   - Try giving it a different name, like `webpack.custom.js`.
   - Run Webpack with a custom config reference (for example, `npx webpack --config webpack.custom.js`).
   - Note how specifying a custom config changes your workflow.

### Part 4: Document Your Findings

- **Take Notes** on what you observe:
  1. What defaults does Webpack use if you provide no config file?
  2. How does changing the folder structure affect the build?
  3. How do you run Webpack with a custom config file?

---

## Submission (Non-Graded)

2. **(Optional) Create a new GitHub repository** or use your existing `webpack-intro` repo to commit any changes you make:
   - Updated folder structure
   - Any config files you used (e.g., `webpack.config.js` or a custom-named file)
3. **Push your changes** and **share your repository link** (if requested) just to show how you experimented.
