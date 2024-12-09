
# CSE 478: Homework #X: UFC Fights Visualization

## Overview

In this assignment, you will use D3.js to visualize data from a large `ufc-master.csv` dataset. The dataset includes thousands of UFC fights with attributes such as fighter odds, dates, winners, finishing methods, and more. Your goal is to provide insights into how fight odds and outcomes vary over time.

**Key Changes:**  
This assignment is simplified compared to previous versions. You will produce **two main visualizations** and may implement a **third optional visualization** for extra credit. Additional extra credit is available for implementing transitions and comparison features.

Data
**Dataset:** `ufc-master.csv` (provided)  
You have access to a large dataset of UFC fights with attributes including date, fighter odds, winner, finishing method, weight class, location, and more.  

You must load and parse the dataset (e.g., convert numeric fields, parse dates) and handle missing data as needed.

## Visualization Requirements

You will create **two main required visualizations** and have the option for extra credit to add a third visualization and additional interaction.

### 0. Set-up (5 points)

- Add a title to your web page: "UFC Fights Visualization"  
- Include your name and email at the top of the page.  
- Add a short introductory paragraph (2-3 sentences) describing what the dataset is and what users can learn from your visualizations.

### 1. Visualization #1: Odds Over Time (30 points)

- Create a **line chart** that shows how the average odds of the "Red" fighter changes over time.  
  - For example, aggregate the data by month (or another suitable time bucket) and compute the average RedOdds for each month.  
  - The x-axis should represent time, and the y-axis should represent the average RedOdds.  
- Add appropriate axes, labels, and a title.  
- This visualization should provide an overall trend of how fighter odds vary over time.

### 2. Visualization #2: Finishing Methods by Selected Month (30 points)

- Below the line chart, create a **bar chart** (or another suitable chart) that shows the distribution of finishing methods (e.g., KO/TKO, Submission, Decision) for a user-selected month (or time period).  
- Provide a simple interface (like a dropdown or a slider) that allows the user to select a specific month (or date range). When changed, the bar chart updates to show the finishing method counts or percentages for that selected month.  
- Add appropriate axes, labels, and a legend if needed.  
- This visualization allows the user to drill down into a specific time period from the line chart to see what types of finishes were most common.

### Extra Credit #1: Third Visualization (up to +10 points)

- Add a **third visualization** of your choice that relates to the data. Some ideas:
  - A scatter plot showing odds vs. fighter height or reach, filtered by a user selection.
  - A heatmap calendar showing the number of fights per day.
  - A stacked bar chart showing finishing methods by weight class.
- This visualization should be distinct from the first two and should provide additional insight into the data.

### Extra Credit #2: Transitions (up to +5 points)

- Add transitions when updating the bar chart for the selected month.  
- For example, when the user picks a new month, the bars should animate to their new heights rather than jump instantly.

### Extra Credit #3: Comparison Mode (up to +5 points)

- Add a comparison feature that allows the user to compare two months side-by-side in the second visualization.  
- For instance, show two sets of bars: one for the currently selected month and one for a user-defined "comparison" month.  
- Include transitions when switching months in comparison mode.

## Code Quality & Comments (5 points)

- Write clear, well-structured, and well-commented code.  
- Briefly summarize your approach and any assumptions at the top of your main JavaScript file.

## Grading Breakdown

- (5 pts) Title, name, introduction  
- (30 pts) Visualization #1: Odds Over Time  
- (30 pts) Visualization #2: Finishing Methods by Selected Month (with interactive selection)  
- (5 pts) Code clarity and comments  
- Extra Credit:  
  - (+ up to 10 pts) Third Visualization  
  - (+ up to 5 pts) Transitions  
  - (+ up to 5 pts) Comparison Mode

**Total possible (without extra credit):** 70 points  
**Maximum with all extra credit:** 90+ points

**Submission:**  
- Submit your HTML, CSS, JS, and `ufc-master.csv` files.  
