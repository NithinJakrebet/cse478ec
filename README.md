

# Homework #X: UFC Visualization with D3 Transitions and Linked Views

## **Overview:**  
For this  assignment, you will create an interactive, multi-view visualization using D3.js to analyze a large UFC dataset. You will produce three linked visualizations that allow users to explore fight trends over time, investigate the distribution of selected attributes, and drill down into finer-grained categorizations through brushing and lasso selection

**Important Notes:**  
- Your final visualization must demonstrate clear and thoughtful design, with axes, legends, and labels that update dynamically.  
- **No starter code provided.** You will write everything from scratch.  
- Cheating or using AI-generated code is not allowed.  

**Dataset**
You will use the provided `ufc.csv` dataset. This is a subset of the dataset `ufc-master.csv`: [(https://www.kaggle.com/datasets/mdabbert/ultimate-ufc-dataset?select=ufc-master.csv)]

The data includes attributes such as:  
- **Date** (fight event date)  
- **Fighter attributes:** RedOdds, BlueOdds, RedAge, BlueAge, RedHeightCms, RedReachCms, and so forth  
- **Categorical attributes:** Finish method (e.g., KO/TKO, Submission, Decision), WeightClass, Country, Gender, Location, TitleBout (True/False)  
- **Quantitative attributes:** Odds, heights, weights, ages, etc.

You may assume that the dataset is located at `data/ufc-master.csv`
- You must support switching to hidden test datasets ("Test1" and "Test2") as well, located at `/data/Test1.csv` and `/data/Test2.csv`.  
- Your code should dynamically parse the datasets.  
- Ensure that changing attributes or datasets do not break your visualization.

## Step 0: Set-Up

1. Create `index.html`, `styles.css`, and `main.js`.
2. Add a title: **"UFC Fights Visualization"**.
3. Include your name and school email 

## Step 1: Control Panel & Dataset Loading

Create a control panel (positioned at the top or side of the page) containing:

1. **Dataset Selector:** A `<select>` to choose from `ufc-master.csv`, `Test1`, and `Test2`. When the dataset changes, you must re-load the data and update all dropdowns and charts accordingly.
2. **Time Aggregation Attribute:** A dropdown to specify how to group fights over time for the first visualization (e.g., by month or quarter).  
3. **Stacked Category Attribute:** A dropdown to choose which categorical attribute to use for a stacked area or stacked bar chart (e.g., Finish method, WeightClass). This will define the segments in the stacked chart.
4. **Distribution Attribute (Beeswarm Plot):** A dropdown for choosing a quantitative attribute (e.g., RedOdds, RedAge, RedHeightCms) to display in a **beeswarm plot**. This attribute will determine the axis position of points.
5. **Color Attribute (Beeswarm Plot):** A dropdown to choose a categorical attribute (e.g., WeightClass, Gender) to color the beeswarm points.
6. **Detail Attribute (Grouped Bar Chart):** A dropdown for selecting which categorical attribute to show in the grouped bar chart that summarizes the selected fights from the beeswarm.

The control panel should be well-labeled and styled. When the user picks new attributes, update the visualizations accordingly with smooth transitions.

## Step 2: Stacked Chart Over Time

Implement a **stacked area chart** or **stacked bar chart** that shows the number of fights over time, segmented by the chosen Stacked Category Attribute. For example, if the user chooses "Finish" as the attribute, each segment in the stack represents a finish type, and the total height shows total fights per time unit.

- The x-axis: Time (based on the selected time aggregation, e.g. monthly or quarterly bins).
- The y-axis: Count of fights.
- A legend should show the color-keyed categories.
- Implement a **brush** on this chart: the user can click and drag over the time axis to highlight a subset of time periods. This brushed selection will filter which fights are displayed in the other views (beeswarm and grouped bar chart).

When the user changes the stacked category or dataset, update the stacks with a transition (e.g., smoothly morph from the old segmentation to the new one).

## Step 3: Beeswarm Plot of Selected Subset

Below or beside the stacked chart, create a **beeswarm plot** that shows the distribution of the selected Distribution Attribute for the fights within the currently brushed time range. If no brush is active, the beeswarm shows all fights.

- The beeswarm plot’s x-axis will represent the chosen quantitative attribute (Distribution Attribute).
- Each point corresponds to one fight, and is colored by the chosen Color Attribute (categorical).
- Include a small legend or color key for the beeswarm categories.

Implement a **lasso tool** on the beeswarm plot:

- The user can click-drag to lasso a subset of points.
- Highlight selected points and de-emphasize others.
- Clicking without dragging resets the selection (no points selected).

Whenever the brushed time range changes on the stacked chart, the beeswarm updates to show only those fights in that time subset. Animate point transitions if the attribute changes (e.g., points move horizontally if the Distribution Attribute changes).

### Step 4: Grouped Bar Chart of Lassoed Points

When the user lassos points in the beeswarm, create or update a **grouped bar chart** that summarizes the selected points by the chosen Detail Attribute (categorical). For example, if Detail Attribute = WeightClass, each bar group represents a category (e.g., Featherweight, Lightweight, etc.), and the height represents the count of selected points in that category.

- If no points are selected, the grouped bar chart should show no bars (or animate them to zero).
- If points become selected, animate the bars growing from zero to their appropriate height.
- When attributes change or the selection changes, update the bars smoothly.

## Step 5: Staged Transitions and Clearing States

- When attributes or datasets change:
  - Animate the stacked chart (e.g., smoothly transition from old stack segments to new).
  - Animate beeswarm points to new positions if Distribution Attribute changes.
  - Clear or update the grouped bar chart accordingly.
- When the brush on the stacked chart changes the time range, smoothly update the beeswarm points (add/remove points, or move them).
- When the lasso selection changes (including clearing it), animate the grouped bar chart to show/hide bars.

## Grading and Submission

- Your solution should be clear, functional, and well-structured.
- Include comments explaining key parts of your code and logic.
- We will test using the provided `ufc-master.csv` and hidden test datasets.
- Submit `index.html`, `styles.css`, `script.js`, and `ufc-master.csv`. Include instructions for any special server needs.

Points (Approximate):  
- Control panel & dataset loading: 2 points  
- Stacked chart & brushing: 3 points  
- Beeswarm plot & attribute changes: 3 points  
- Lasso and linked grouped bar chart: 2 points  
- Staged transitions & design quality: ~1 points  

**Total (without extra credit):** 11 points 
