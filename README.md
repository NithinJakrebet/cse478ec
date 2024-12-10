# Homework #X: UFC Visualization with D3 Transitions and Linked Views

## Overview

In this assignment, you will build an interactive, multi-view visualization using D3.js to explore a UFC dataset. You will create three linked visualizations:

1. A stacked chart over time to understand fight trends.
2. A beeswarm plot to show the distribution of selected attributes.
3. A grouped bar chart that summarizes subsets selected via lassoing points in the beeswarm.

You will implement controls, brushing, lassoing, transitions, and dynamic updates as the user interacts with the interface.

**Important:**  
- Write all code from scratch (no starter code).  
- Must use D3 joins, transitions, and dynamic updates.  
- No cheating or using AI-generated code. 

## Data
The dataset is `ufc.csv` located at `data/ufc.csv` (a subset of [ufc-master.csv](https://www.kaggle.com/datasets/mdabbert/ultimate-ufc-dataset?select=ufc-master.csv). Support switching to hidden test datasets (`Test1.csv` and `Test2.csv`) as well.

Contains date, fighter attributes (odds, age, height, reach), categorical attributes (finish method, weight class, country, etc.), and more.

You will also add options for `Test1.csv` and `Test2.csv`, located at `data/Test1.csv` and `data/Test2.csv`  (which we will provide during grading). Your code should handle them gracefully.

## Step-by-Step Requirements

### Step 0: Setup

- Create `index.html`, `styles.css`, `main.js`.  
- Add a title: "UFC Fights Visualization".  
- Include your name and email.

### Step 1: Control Panel

Create a control panel with the following selects:

- **Dataset Selector:** Choose `ufc.csv`, `Test1`, `Test2`.  
- **Time Aggregation:** How to group fights over time (e.g., by month or quarter).  
- **Stacked Category Attribute:** A categorical attribute to segment the stacked chart.  
- **Distribution Attribute (Beeswarm):** A quantitative attribute for the beeswarm’s x-axis.  
- **Color Attribute (Beeswarm):** A categorical attribute that colors the beeswarm points.  
- **Detail Attribute (Grouped Bar):** A categorical attribute to summarize lassoed points.

When any control changes, update the visualizations accordingly.

### Step 2: Stacked Chart Over Time

- Implement a stacked area or bar chart showing the count of fights over time.  
- Segments represent categories chosen by the Stacked Category Attribute.  
- Add a brush so the user can select a time range. This filters the data shown in the beeswarm and grouped bar chart.

When dataset or category changes, animate the stacked chart’s transitions.

### Step 3: Beeswarm Plot

- The beeswarm plot shows the distribution of the chosen Distribution Attribute for the currently brushed time range.  
- Color the points by the selected Color Attribute.  
- If no brush is active, show all fights.  
- Update and animate points when attributes change.

### Step 4: Lasso & Grouped Bar Chart

- Implement a lasso on the beeswarm plot to select points.  
- Selected points are highlighted, others de-emphasized.  
- When points are selected, draw a grouped bar chart summarizing them by the chosen Detail Attribute.  
- If no selection, show no bars (or animate bars to zero).

### Step 5: Transitions & Updates

- On attribute or dataset changes, animate the stacked chart and beeswarm points.  
- On brushing changes, update the beeswarm points smoothly.  
- On lasso changes, animate the grouped bar chart.

## Grading & Submission

- Submit `index.html`, `styles.css`, `main.js`, and `ufc.csv`.  
- We will test with `ufc.csv` and hidden test sets.  
- Points (approximate):  
  - Control panel & dataset loading: 2 pts  
  - Stacked chart & brushing: 3 pts  
  - Beeswarm & attribute changes: 3 pts  
  - Lasso & grouped bar: 2 pts  
  - Design & transitions: 1 pt  
**Total: 11 points**
