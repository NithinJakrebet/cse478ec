**CSE 478: Homework #X (Extra Credit)**  
**Title:** Visualizing UFC Fights: Odds, Winners, and More

**Overview:**  
In this assignment, you will create an interactive, animated data visualization using D3.js. You’ll be visualizing mixed martial arts fight data from the provided UFC dataset. Your visualization should help users explore how fight outcomes and betting odds vary over time, weight classes, and countries. You will use D3 joins to bind data to your visual elements, transitions to animate changes to the visualization, and an interactive timeline slider or playback button to filter and display fights from different event dates.

This assignment is designed to test your skills in:  
- Data joins and updates when filtering or changing parameters  
- Animated transitions in D3  
- Implementing a time-based "playback" or slider interface  
- Encoding multiple data attributes (e.g., winners, odds, and fight outcomes) in a meaningful way

**Data Source:**  
You will be using a subset of the data from `ufc-master.csv` (provided in the starter code folder). This dataset includes details about UFC fights such as fighter names, odds, expected values, dates, winners, weight class, gender, location, and finishing methods, among others.

**Your Task:**  
You will create a web-based visualization (using D3 v7 or later) that allows users to explore how fight outcomes and betting odds vary by date and weight class. Specifically, you’ll implement the following features:

### 0. Setup & Housekeeping (5 points)  
- **Title & Identification:** At the top of your HTML page, add a title for the visualization: "UFC Fights: Odds & Outcomes".  
- Add your name, email, and date submitted at the top as well.  
- Include a brief one-paragraph introduction describing what the dataset is and what users can learn from your visualization.

### 1. Load & Process the Data (10 points)  
- Load the provided `ufc-master.csv` dataset using D3.  
- Parse dates properly (the `Date` field is in YYYY-MM-DD format).  
- Filter out rows with missing essential information (e.g., fights with empty odds). Document your filtering criteria in comments.  
- Create derived fields if needed. For example, you may want to create a categorical variable indicating "favorite" (the fighter with the lower absolute odds) versus "underdog," or separate data into date buckets (e.g., by year or month).

### 2. Static Visualization: Aggregation by Time & Weight Class (20 points)  
- Create an SVG-based chart that initially shows aggregated information over a specified time period.  
  - For example, show a bar chart of the average "RedDecOdds" (or another odds measure) by major weight classes (e.g., Heavyweight, Lightweight, Bantamweight, etc.) for fights that occurred during the first quarter of 2024.  
- Each bar should represent a weight class, and the height should encode the average odds of the red-corner fighter (or a chosen metric).  
- Add axes, a legend if needed, and clearly label your chart and axes.

### 3. Interactivity: Filtering by Date via a Slider or Playback Button (25 points)  
- Add a horizontal date slider or a step-based "play/pause" button that lets the user control which date (or date range) of fights they are viewing.  
- When the user moves the slider or clicks a "play" button, the visualization should update to reflect the fights for that selected date or date range.  
  - For example, if the slider moves from January to February 2024, the bars should update to show the aggregated average odds for only the February fights.  
- This step requires you to implement proper data joins and updates. You should transition the bars to their new heights smoothly, using D3 transitions. No instant jumps!

### 4. Animated Transitions (20 points)  
- When the user changes the date, update the visualization with a transition.  
  - Bars should animate from old values to new values (height changes should be visible).  
- Include at least one other transition effect. For example, you could fade out and in the y-axis scale or position labels as the data changes.  
- The transitions should be smooth, taking about 750 ms to 1 second.

### 5. Adding Fighter-Level Detail on Hover (15 points)  
- When a user hovers over a bar, show a tooltip or a secondary display that highlights detailed fighter-level information for the chosen time frame and weight class.  
  - For example, display the number of fights in that class, the name of a top fighter (e.g., the fighter who had the best odds), or the most common finishing method during that period.  
- This detail view should update each time the main display changes date ranges.  
- The tooltip should appear near the mouse and disappear on mouseout.

### 6. Extra Interface Element: Compare Two Dates (Optional Extra Credit, up to +5%)  
- Add a second slider or a toggle that lets the user compare two distinct date ranges side-by-side.  
  - For instance, draw two sets of bars: one for the current selected date range and one for a historical date range. Animate transitions as the user changes the comparison period.  
- This comparison feature is optional but can help you earn additional credit.

### 7. Code Quality & Comments (5 points)  
- Your code should be well-structured and commented.  
- Variables and functions should have meaningful names.  
- Include a brief README section at the top of your JavaScript file that summarizes your approach and any assumptions.

**Hints & Reminders:**  
- Don’t forget to convert numerical values from strings using `+` or `parseFloat`.  
- For date parsing, use D3’s time parsing utilities.  
- Carefully consider your data joins. On each update (when the slider changes), some weight classes may appear or disappear in that timeframe. Ensure you handle enter/exit selections correctly.  
- Try to keep the visualization simple and clear. A good initial guess might be to focus on about 4-6 major weight classes.  
- Consider using `d3.scaleTime` for the slider and `d3.brushX` or an HTML input element for the date slider.  
- For transitions, remember `.transition()` and `.duration()` methods on selections.

**Submission Instructions:**  
- Submit your HTML, CSS, and JS files along with any supporting files.  
- Include the dataset or ensure your code loads `ufc-master.csv` from the provided location.  
- Provide a link or instructions to run your code on a local server.

**Grading Breakdown (100 points + optional extra credit):**  
- (5 pts) Title, name, introduction  
- (10 pts) Data loading and processing  
- (20 pts) Initial static visualization  
- (25 pts) Interactive slider/date control and filtering  
- (20 pts) Smooth transitions and animated updates  
- (15 pts) Hover tooltip with fighter-level details  
- (5 pts) Code quality, clarity, and comments  
- (+ up to 5% extra) Comparison mode or other creative interactive features

We look forward to seeing your creative solutions and how you leverage transitions, filtering, and D3’s core functionalities to tell a story about UFC fights!
