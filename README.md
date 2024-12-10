# Homework #X: UFC Visualization with D3 Transitions and Linked Views

## Overview

In this assignment, you will create an interactive, multi-view visualization using D3.js. Building on the skills you've developed in previous homeworks, you will apply data joins, transitions, brushing, and lasso-based interactions to explore a dataset of UFC (Ultimate Fighting Championship) fights. Your visualization will integrate several coordinated views:

1. A stacked chart over time to understand fight trends.
2. A beeswarm plot to show the distribution of selected attributes.
3. A grouped bar chart that summarizes subsets of fights selected via a lasso.

Your page will include a control panel allowing users to switch datasets, select attributes, and dynamically update the views. This assignment tests your ability to combine multiple D3 techniques—data aggregation, filtering, transitions, and interactive elements—in one coherent interface.

**Important Notes:**  
- No starter code is provided; you must write everything from scratch (HTML, CSS, JS).
- You should produce a clear, thoughtful design with consistent styling and intuitive interactions.
- All code must be your own. No code sharing or AI-generated code allowed.

## Dataset

You will use the provided `ufc.csv` dataset, which is a subset of the [ufc-master.csv dataset from Kaggle](https://www.kaggle.com/datasets/mdabbert/ultimate-ufc-dataset?select=ufc-master.csv). The data includes:

- **Dates** of fights
- **Fighter attributes:** Odds, Age, Height, Reach, etc.
- **Categorical attributes:** Finish method (KO/TKO, Submission, Decision), WeightClass, Country, Gender, Location, TitleBout (True/False)
- **Quantitative attributes:** Various numeric measurements (odds, height in cm, age, etc.)

Additionally, you must support two hidden test datasets (`Test1.csv` and `Test2.csv`) located in the same folder. Your code should handle dynamic changes to these datasets without breaking.

## Setup

1. Create an `index.html` file and corresponding `styles.css` and `main.js` files.
2. At the top of your `index.html`, add the title **"UFC Fights Visualization"**, as well as your name and school email.

## Step-by-Step Requirements

### Step 1: Control Panel & Dataset Loading (2 points)

Create a control panel with the following HTML controls:

- **Dataset Selector:** A `<select>` to choose between `ufc.csv`, `Test1.csv`, and `Test2.csv`. Changing this re-loads data and updates all other visualizations.
- **Time Aggregation:** A dropdown to choose how to aggregate fights over time (e.g., by month or quarter).
- **Stacked Category Attribute:** A dropdown to select a categorical attribute for the stacked visualization segments (e.g., Finish method).
- **Distribution Attribute (Beeswarm):** A dropdown to pick a quantitative attribute that determines the x-axis position of points in the beeswarm plot.
- **Color Attribute (Beeswarm):** A dropdown for a categorical attribute that determines point colors in the beeswarm.
- **Detail Attribute (Grouped Bar):** A dropdown for a categorical attribute that groups fights in the bar chart based on the lasso selection.

When any of these controls change, all relevant visualizations must update accordingly using D3 transitions.

### Step 2: Stacked Chart Over Time (with Brush) (3 points)

Create either a **stacked area chart** or a **stacked bar chart** that shows how the count of fights changes over time. The time axis should reflect the chosen Time Aggregation method. Segments in the stack represent categories defined by the chosen Stacked Category Attribute.

- Include axes and a legend mapping categories to colors.
- Implement a **brush interaction** along the time axis, allowing the user to select a time range. Only fights from the brushed time range should appear in the subsequent views (beeswarm and grouped bar).
- When switching datasets or attributes, animate the stacked chart transitions (e.g., smoothly morph from one stacked configuration to another).

### Step 3: Beeswarm Plot of Filtered Data (3 points)

Create a **beeswarm plot** that displays the distribution of the currently filtered fights (based on the stacked chart brush) along the chosen Distribution Attribute (quantitative). Each point represents a single fight:

- Position each point along the x-axis based on the Distribution Attribute.
- Color points by the chosen Color Attribute.
- Include a color legend.
- If no brush is active, the beeswarm shows all fights.
- On dataset or attribute changes, smoothly transition points to new positions or add/remove points as needed.

### Step 4: Lasso & Grouped Bar Chart (2 points)

Implement a **lasso selection** on the beeswarm plot:

- The user can click and drag to draw a freeform polygon selecting a subset of points.
- Highlight selected points, dim non-selected points.
- Clicking without dragging clears the selection (no points selected).

Based on the lassoed points, draw a **grouped bar chart** that summarizes these selected fights by the chosen Detail Attribute. For example, if Detail Attribute = WeightClass, each bar represents a specific weight class, and the bar height corresponds to the count of selected fights in that category.

- If no points are selected, show no bars (or animate them down to zero).
- Update and animate the grouped bar chart whenever the lasso selection changes or attributes update.

### Extra Credit: Staged Transitions & Dynamic Updates (1 point)

Ensure all changes—dataset switches, attribute changes, brushing updates, lasso selections—result in smooth, meaningful D3 transitions:

- Animate stacked segments as attributes or datasets change.
- Animate beeswarm points when the distribution attribute or filtered data changes.
- Animate grouped bars when the selection or detail attribute changes.

Strive for a cohesive, responsive UI that makes it easy for users to understand how the data changes in each view.
