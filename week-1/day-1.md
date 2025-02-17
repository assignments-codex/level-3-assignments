# Assignment 1 (Day 1): Installing Node.js and Exploring Terminal Outputs

## Objective

- Ensure you have Node.js installed and properly configured.
- Practice using the terminal to run basic Node.js commands.
- Create and execute a simple JavaScript file through Node.

## Instructions

### Part 1: Install and Verify Node.js

1. **Install Node.js**:
   - Download and install the LTS version of Node.js from [Node.js official site](https://nodejs.org/).
2. **Verify Installation**:
   - Open your terminal and run `node -v`.
   - Take note of the Node.js version installed (e.g., `v16.x.x` or similar).

### Part 2: Exploring the Node.js REPL

1. **Enter REPL Mode**:
   - Type `node` in your terminal and press Enter to enter the Node.js REPL (Read-Eval-Print Loop).
2. **Test JavaScript in REPL**:

   - Type a few JavaScript statements, for example:


     `console.log("Hello from Node REPL!"); 2 + 2`

   - Observe the outputs.

3. **Exit REPL**:
   - Type `.exit` or press `Ctrl + C` twice to exit.

### Part 3: Create a Simple Node.js Script

4. **Create a File**:
   - In a new folder (e.g., `node-basics`), create a file named `index.js`.
5. **Write Some Code**:

   - In `index.js`, add the following code:

     `console.log("Welcome to Node.js!"); console.log("The current date and time is:", new Date());`

6. **Run the File**:
   - In your terminal, navigate to the folder containing `index.js`.
   - Run the script with `node index.js`.
   - Verify the output appears in the terminal.

### Part 4: Document Your Steps (Optional Screenshot)

- If possible, take a screenshot showing:
  1. `node -v` output.
  2. Your terminal running `node index.js` and displaying the results.

## Submission

- **GitHub Repository** (Optional):
  - If instructed, create a repository named `node-basics`.
  - Include `index.js` with the code you wrote.
- **Submission Link**:
  - Submit the URL to your GitHub repository.

## Rubric

| Criteria                        | Limited (0 pts)                                        | Partial (3 pts)                                                  | Complete (5 pts)                                                            |
| ------------------------------- | ------------------------------------------------------ | ---------------------------------------------------------------- | --------------------------------------------------------------------------- |
| **Node.js Installation**        | Node.js not installed or unable to verify via terminal | Node.js installed but terminal verification incomplete           | Node.js installed, verified, and version noted                              |
| **Basic Terminal Usage**        | Did not use terminal commands correctly                | Some familiarity but commands not fully utilized or demonstrated | Demonstrates correct usage of commands, including REPL and script execution |
| **Script Creation & Execution** | No JavaScript file created or executed                 | Script created but not executed correctly or has errors          | Script created, run successfully, and produces expected output              |
| **Code Quality & Organization** | Code is difficult to read or poorly structured         | Code is somewhat clear but could be improved                     | Code is well-organized, easy to read, and follows best practices            |
