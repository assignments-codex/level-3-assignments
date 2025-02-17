# Assignment 2 (Week 3, Day 3): Single-Day Weather App with `useEffect`

## Objective

- Learn how to **fetch data** in React using `useEffect`.
- Practice **displaying and updating state** with real-time weather data.
- Strengthen understanding of **component lifecycle** in a functional React component.

## Instructions

### Part 1: Project Setup

1. **Create or Reuse a React App**
   - You may continue from your previous React-Vite project or create a new one.
2. **Install Necessary Packages** (Optional)
   - If you plan to use **axios** or similar for data fetching, install it as a dependency (or use `fetch`).

### Part 2: Implement `useEffect` for Weather Data

1. **Choose an API**
   - For example, the OpenWeatherMap API.
   - Get an **API key** if required (usually free tier sign-up).
2. **Create a Component**
   - Could be named `Weather`, `WeatherApp`, or something similar.
   - Inside, use:
     - `useState` for storing weather data and any potential errors.
     - `useEffect` to fetch the weather data when the component mounts or when a specific city name changes.
3. **User Input (Optional Enhancement)**
   - Let the user type in a city name. When they press a button, your app should fetch and display that city’s current weather.

### Part 3: Display the Weather

4. **Render Basic Information**
   - For instance, show the city name, temperature, weather description, and an icon (if desired).
5. **Handle Loading & Errors**
   - Consider showing a “Loading…” message or a simple indicator while fetching data.
   - Display a friendly message if the user enters an invalid city or if the fetch call fails.

### Part 4: Test the App

- **Run Your App** and open it in a browser.
- Verify the weather data displays and updates correctly when you change the city.

---

## Submission

- **GitHub Repository**
  1. Create a repository named `single-day-weather`.
  2. Commit and push your React project files, including:
     - `package.json` (and `package-lock.json` or `yarn.lock`, if applicable)
     - Your React source code (`src` folder) showing the `useEffect` usage
     - Any configuration or `.env` file (if relevant) **but do NOT commit sensitive API keys**
  3. Provide the GitHub repository URL as your submission.

---

## Rubric

| Criteria                               | Limited (0 pts)                                | Partial (3 pts)                                                | Complete (5 pts)                                                                                   |
| -------------------------------------- | ---------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **1. Project Setup & Data Fetch**      | No React setup or data fetch call made         | Basic setup with incomplete or failing fetch process           | Project initialized correctly and data fetch works as intended                                     |
| **2. `useEffect` Implementation**      | No usage of `useEffect`                        | `useEffect` used but not fully correct or triggers excessively | Properly implemented `useEffect` for fetching data or reacting to state changes                    |
| **3. Weather Data Display**            | No displayed weather info or incomplete render | Weather data rendered but minimal or partially broken          | Complete data render (city, temperature, description, etc.) with clear UI presentation             |
| **4. Code Organization & Readability** | Disorganized component/files, hard to follow   | Some structure but still unclear or inconsistent               | Well-structured React components, readable code, logical state management                          |
| **5. Error & Loading Handling**        | No handling of errors or loading states        | Partial handling but error messages or loading states unclear  | Clear user feedback for loading/error states; gracefully handles invalid inputs or failed requests |
