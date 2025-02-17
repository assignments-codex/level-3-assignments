# Task (Week 3, Day 4): Mapping Data for a 7-Day Weather Forecast

## Objective

- Extend your existing weather app to **fetch and display multiple days** of weather data.
- Practice **mapping over arrays** of data in React to render multiple components or elements.
- Gain experience handling **more complex response structures** from a weather API.

## Instructions

### Part 1: Choose or Create a Base

1. **Continue from Day 3**
   - Use the single-day weather app you built with `useEffect`.
2. **API Endpoint for Multi-Day Forecast**
   - Check your chosen weather API (e.g., OpenWeatherMap) for a 5-day or 7-day forecast endpoint.
   - Update your fetch call or create a new fetch function to retrieve the **extended forecast** data.

### Part 2: Map Over the Forecast Data

1. **Structure Your State**
   - Store the forecast array (e.g., daily or 3-hour intervals) in a React state variable.
   - Consider creating a separate piece of state from the single-day data, or replace it entirely with multi-day data.
2. **Render Multiple Days**
   - Use `Array.map()` in your JSX to loop over each day/interval in the forecast.
   - Display relevant info: date/time, temperature, conditions, etc.
3. **Styling or Layout** (Optional)
   - Arrange the items in a list or grid.
   - You can simply list them if you prefer a minimal approach.

### Part 3: Error Handling and Edge Cases

- Ensure that if you **don’t** find data for a city, or if the API fails, you handle it gracefully (e.g., show an error message or fallback text).
- Consider a **loading** state while the forecast data is being fetched.

### Part 4: Test the Expanded App

- **Run your app** to confirm you see multiple entries for each day.
- Double-check the console for errors, especially if the API response format differs from what you expect.

---

## Additional Notes (Non-Graded)

- Feel free to commit and push your changes to a GitHub repo for personal reference (e.g., `multi-day-weather` or continue in the same repo).
- Look at the weather API documentation for details on the response format, units, and time intervals.
