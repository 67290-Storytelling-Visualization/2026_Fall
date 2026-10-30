# Lab 2 · Tableau and Integration in Observable Dashboard

**67-290 Storytelling with Data Visualization · CMU-Qatar · Saturday 31 October 2026 · 90 minutes · 5 points**

This lab walks through publishing a Tableau visualization and embedding it into your Observable dashboard, either
directly in HTML or through an Observable notebook cell.

## Files in this folder

| File | Purpose |
|---|---|
| `README.md` | Full lab instructions (this page) |
| `data/arrests.zip`, `data/blotter.zip` | The two datasets for Part 1 |
| `images/` | Images used on this page |
| `tableau-embed.html` | Starter file for Option 1 (HTML embed) |
| `tableau-notebook.ojs` | Starter file for Option 2 (Observable embed) |

## Before class

1. To register for a Tableau Public Account, visit https://public.tableau.com/en-us/s/
2. Get the lab files onto your laptop. In a terminal, navigate to the folder of your choice using 'cd ' command, then run:

   ```
   git clone https://github.com/67290-Storytelling-Visualization/Lab2_Fall2026.git
   ```

   This downloads the Lab 2 files into a `Lab2_Fall2026` folder. Open `Lab2_Fall2026/data` and unzip `arrests.zip`
   and `blotter.zip` there.

---

# Part 1 · Getting Started with Tableau

## Workshop Exercises

Sample output dashboard (see below)

![Sample output dashboard](images/sample-dashboard.png)

Data for these exercises comes from the Western PA Regional Data Center website. Use the `.csv` files you unzipped
before class, in `Lab2_Fall2026/data`:

- **Dataset 1:** Police Blotter Data (UCR Coded), `blotter.csv`: https://data.wprdc.org/dataset/uniform-crime-reporting-data
- **Dataset 2:** Arrests, `arrests.csv`: https://data.wprdc.org/dataset/arrest-data

To start, sign in at [public.tableau.com](https://public.tableau.com) and choose **Create → Web Authoring**. Tableau
Public does not save automatically, so publish your work now and then (see Exercise 8).

### Exercise 1: Connect to the Pittsburgh crime datasets

Our first exercise involves uploading our data into Tableau. We can do this from the 'Connect to Data' window. In this
window, we can see multiple places from which we can access datasets and the types of datasets we can add.

- **Connect to a dataset:** Choose 'Files' 'Upload from computer'. From there, select one of the two city crime data files
  from `Lab2_Fall2026/data` (start with `arrests.csv`).
- Once you have uploaded this file, you will be taken to the 'Data Source' pane. You can switch to this pane at any
  time by selecting the 'Data Source' tab at the bottom of the Tableau window.
- We still need to add our second data set. From the 'Connections' section at the top left of the Tableau window,
  select 'Add'. From here, you will see a window pop up that looks like the connect page where we uploaded the first
  file. Follow the same process as above to add the second dataset.

Once at the data source pane, under 'Files', drag `blotter.csv`over to the large white space, right next to `arrests.csv`. Tableau asks how
the two files are related.

- Under arrests.csv choose 'CCR', and under blotter.csv choose 'CCR (blotter.csv)', so that Tableau joins on the CCR
  field (this is a unique incident report number assigned to crime incidents in the blotter and arrest files).

**What is a join?** The two files describe different things. `arrests.csv` has one row per person arrested (their
age, gender, offense and location). `blotter.csv` has one row per incident the police recorded (what kind of incident
it was, when and where). Both have a `CCR` column, the incident's report number. A join matches the rows that share a
CCR, so each arrest is linked to the incident it came from. For example, CCR 16158872 is a 42-year-old woman arrested
for retail theft in `arrests.csv`, and a shoplifting incident in Bloomfield in `blotter.csv`. (Tableau calls this link
a relationship.)

Once the files are linked, one chart can use columns from both. In Exercise 5, for example, you will map arrests from
`arrests.csv`, but only those for marijuana incidents, a column in `blotter.csv`. Not every row finds a partner: almost
every arrest matches an incident, but only about one incident in six led to an arrest.

Click on the Sheet 1 tab at the bottom of the window. We are now ready to start visualizing our data!

### Exercise 2: Build a contingency table of offender gender by age group

For our first visualization, let's make a table. In many cases, instead of making a graph, a table can be a great way
to visualize data so your audience can understand it quickly. Tableau also makes it easier to incorporate multiple
variables in many configurations to create attractive tables.

To make a contingency table in Tableau you need to work with both 'Dimensions' and 'Measures':

| | Dimensions | Measures |
|---|---|---|
| **What they are** | Categories you group by (qualitative) | Numbers you count, add up or average (quantitative) |
| **Color** | Blue | Green |
| **Where** | Left side of the screen, above the thin gray line | Below the thin gray line |
| **Examples in this lab** | `Gender`, `Incidenthierarchydesc`, `Incidenttime` | `arrests.csv (Count)`, and `AGE` until you change it below |

Tableau sorts fields into the two groups automatically, but it can guess wrong. The icon next to each field shows its
type: 'abc' for text, '#' for numbers, and other icons for dates and geographic data.

- **Make a table:** To make a contingency table based on the offender's age and gender, we need to change our 'AGE'
  variable from a 'Measure' to a 'Dimension'. To do this, drag the 'AGE' variable (in the arrests.csv list) from the Measure's section to the
  Dimension's section.
- Now that both AGE and 'Gender' are Dimensions we can create a table based on these variables.
- Drag Gender to Columns input and AGE to the Rows input.

You can see that there is now a table that compares AGE to Gender. However, all the places that should have values are
denoted by 'abc'. This indicates that there is no quantitative information currently available in this table.

- **Adding counts to a table:** To add our counts for each variable, select 'arrests.csv (Count)' under 'arrests.csv'. Drag this variable
  to the 'Text' box within the 'Marks' card, which is to the left of the graphing space and to the right of the
  Dimensions section. You will now see that there are counts of each group of offenders by age and gender.

However, this is not a very concise table. We can assume that it would be more useful to group different ages
together, to make the table easier to read.

- **Exclude null values:** Before grouping, clean up the table by excluding null and incorrect values. In this dataset
  you may see age values for NULL, 0, 117 and 999. These are not real ages but missing or mistyped entries. Simply
  right click on these and choose Exclude from the dropdown menu.
- **Creating age groups:** To group our age variables together by increments of several years (Under 18, 18-25,
  26-40, 41-65, Over 65), start by creating the first grouping. This can be done by selecting at once all ages between
  10 and 17, by clicking on 10 in the table, holding the shift key down and clicking on 17. Once these have been
  selected, right-click one of the selected ages and choose 'Group'.

This will then combine the counts for ages between 10 and 17.

- **Rename groups and variables:** To rename the label for this group, right click on the label that now says
  '10,11,12…,17' and select the dropdown field Edit Alias. A new field will pop up, allowing you to relabel the grouped
  variables. Rename this field 'Under 18'.
- Now, continue to group the age variable to showcase counts of crimes by age and gender as age groups. For example,
  create groups for 18-25, 26-40, 41-65 and Over 65.
- **Reordering rows:** You can reorder the age groups by dragging and dropping. Move the Under 18 age group to the top
  of the column.
- **Adding color:** To add further context, you can drag the 'CNT(arrests.csv)' measures from the marks card variable
  to color. This will create a heat map within the table, with darker colors showing where the highest values are
  centered. To add in the text label, click the T icon located in the menu bar.
- **Adding totals:** To add more detail to our table, we can add totals fields. To do this, toggle from the 'Data' tab
  that shows our dimensions and measures, to the 'Analytics' tab. From here, click and drag 'Totals' to the table.
  Choose to add row or column totals, or you can add both by dragging twice.

### Exercise 3: Visualize offender age group and gender in a stacked or side-by-side bar chart

Now that we have made a table, it will be easy for us to explore the same information as a bar chart. Typically, bar
charts are a great way to compare values across categories as humans are adept at comparing lengths and have been
trained to do so in the context of a bar chart.

- **Create and name a new sheet:** Before we begin, at the bottom of the screen, start a new sheet. Label this sheet something that will be
  meaningful for your analysis, such as "Offender age Group and Gender".
- **Create a Bar Chart:** To create a bar chart based on gender and age, first bring the 'arrests.csv (Count)' variable
  to the columns bar. Then bring the grouped 'AGE' field from our 'Dimensions' table to the rows bar. This will be a new
  field based on the groupings we did in the last chart. It will be shown as the 'AGE' with a paperclip and not an '#'
  next to it.
- **Exclude null values again:** Null, 0, 117 and 999 are back, because an Exclude only applies to the sheet where you
  made it. Right click on each of them and choose Exclude, as in Exercise 2.
- **Stacking variables:** We now have a bar chart showing Age by groups from exercise 2. To add gender to our
  visualization, drag 'Gender' to Color in the Marks card. You now have a stacked bar chart by our age categories, with
  Female designation represented in blue and Male represented in orange. You may want to change these colors, as your
  audience will likely associate the color blue with Male. This may cause them to misread your graph.
- **Working with color:** To change the color of 'Gender' within your visualization, click the 'Color' box within the
  'Marks' card. This will open a new window which allows you to edit the colors in your visualization, as well as the
  shade. Select 'Edit Colors'. This will pull up an additional window which will allow you to directly edit colors.
  You can either click on each variable color square to change it within the visualization, or you can select an
  entirely new color scheme with the dropdown bar under 'Select Palette'. Select the 'Traffic Light' option, then press
  'Assign Palette' to finalize your choice. Now your Male and Female color palette is less likely to confuse. If you
  like, you can also play around with other color palette options at any time.
- **Side-by-side bar chart:** You can also choose to represent these variables, age and gender, side by side. To do
  this, pull 'Gender' from the 'Dimensions' list to the rows bar. Make sure to place it after the 'AGE (group)'
  variable. This way the visualization will group all ages together, showcasing changing numbers of incidents for men
  and women of the same age side by side.
- **Grouped bar chart:** Additionally, if you would like to view Male and Female incidents separately, drag the
  'Gender' Variable before the 'AGE (group)' variable in the rows bar. This will reorder your visualization by Gender
  first.
- **Reordering rows and columns:** You can also order your columns or rows variables by dragging them into different
  positions along the axis bar. Try this by moving the 'Under 18' category to be first variable along the axis.
- **Final version:** For your dashboard, end with the stacked bar chart. Remove 'Gender' from the rows bar, so that only
  'AGE (group)' is on the rows bar and 'Gender' is on Color, with 'Under 18' first. This is the 'Age by Gender Bar
  Chart' in the sample dashboard above.
- Label and name your sheet.

### Exercise 4: Visualize marijuana sales vs. possession incidents by month

Line graphs are also excellent ways to view information, especially if that information is related to change over
time. To examine this, we can track changes for marijuana sales over time.

- Add a new sheet.
- **Using filters:** First, we need to use a filter to extract Marijuana sales and possession incidents from the
  'Incidenthierarchydesc' Dimension category (under 'blotter.csv'). To do this, first drag the 'Incidenthierarchydesc' to the Filters card,
  above the Marks card. In the window that opens, choose to select only the variables we want; in this case, Marijuana
  sales and possession incidents or 'MARIJUANA-POSSESS' and 'MARIJUANA-SALE/MFG' (type MARIJUANA in the search box to
  find them), and click OK. As we have selected only this information, our visualization will only return information on
  Marijuana related incidents.
- **Create a line graph:** To create a line graph that shows the trends in this information over time, take the
  'Incidenttime' from the Dimensions field and place it in the columns bar. Then, bring 'blotter.csv (Count)' over to
  the rows bar. You should now have a line graph representing the total count of all Marijuana incidents between 2016
  and 2023 (some older reports are dated 2005). We can assume that these are the years that are included in our data
  set.
- **Start from 2016:** There are no reports between 2005 and 2016, so the 2005 reports would leave a long gap, which
  later becomes a straight line across ten years without data. Drag 'Incidenttime' to the Filters card, choose
  'Years', untick 2005, and click OK.
- In the columns bar, you can see that the 'Incidenttime' pill has converted to read years with a + mark in front of
  it. This is indicating that though Tableau will automatically show years associated with our variables, there is
  more information we can access through this pill. If we click the drill down button (plus mark in the year pill) we
  can move through to Quarters and, repeating the drill down function on the Quarters pill to Months. Remove Quarters
  from the columns bar. This creates a small multiples graph of incidents by month in every year.
- The reason that the years are shown as separate entities and not continuous is that years are still being treated as
  a Dimension (or categorical singular variables) rather than as a Measure (qualitative and 'continuous'). In order to
  view the change in marijuana sales over time as a continuous spread, we need to change the time pills in our columns
  bar from Dimensions to Measures. To do this, first remove months from the columns bar. Then right click on the year
  pill in the columns bar. In the drop-down list, you can see there are two years. The first year, which you can see
  is pre-selected, is our dimension (discrete) year value. Select the second year (or the measures year). This will
  change the year to a measures pill.
- You can now see one continuous spread of information for change in incidents over every year. If we drill down now,
  instead of keeping Year as an overarching category for Quarter to fall into, Quarter replaces Year. If we drill down
  again, we now have the continuous spread of data from the date of the first data point to the date of the last data
  point.
- To view 'MARIJUANA-POSSESS' and 'MARIJUANA-SALE/MFG' as separate lines within this graph, drag over the
  'Incidenthierarchydesc' pill from our the Dimension's List on the left hand side of the Tableau viewframe and drop it
  into the color box within the 'Marks' Card. This will automatically show 'MARIJUANA-POSSESS' and
  'MARIJUANA-SALE/MFG' as two separate lines and in different colors.
- Save and label your sheet.

### Exercise 5: Create a map of all crimes color-coded by council district

- Add a new sheet. We will now make a map that will showcase the spatial nature of this data set.
- To do this, we first need to transition the X and Y coordinates from numerical fields to geospatial fields. Use the
  'X' and 'Y' in the arrests.csv list. Right click on the 'X' pill in the measures column. From the
  resulting drop down menu select geographic role, then Longitude. Repeat this process with the 'Y' pill, but select
  Latitude. You can now use these two pills as geographic coordinates.
- Now take the 'X' pill to the columns bar and the 'Y' pill to the rows bar. There should now be a map in the
  visualization space.
- Filter this sheet to only Marijuana incidents, as in Exercise 4: drag 'Incidenthierarchydesc' to the Filters card
  and select 'MARIJUANA-POSSESS' and 'MARIJUANA-SALE/MFG'. You need to do this again because a filter only applies to
  the sheet where you made it.
- To bring out our Pittsburgh points, we need to adjust our 'X' and 'Y' pills so they are not represented as an
  average value. To do so, right click on each of the geographic pills in the columns and rows bars. From the resulting
  drop down menu change the pill from a Measure (which is automatically selected) to a Dimension.
- Now refocus the map by hovering your mouse over the visualization pane and selecting from the pop up tab that appears
  on the left side of your map. This is the map control pane that will let you refocus the view of your map within the
  Tableau window. Choose the arrow at the bottom of the pop up bar—this will open more options to navigate the map.
  Click the button that has a square covered by a magnifying glass. This will allow you to drag a box over points on
  the map to zoom into those points.
- Next change the 'Council District' pill (in the arrests.csv list) to a Dimension pill following the steps we used for 'AGE'. Then, bring the
  pill to the 'Color' box in the 'Marks' Card. You can see there are now multiple points that are colored by council
  district, which provides us some context for differences within the map. However, these points are still hard to
  distinguish.
- To make the map easier to read, drag the Measure pill 'arrests.csv (Count)' to the 'Size' box within the 'Marks'
  Card'. This will now create and order of size by number of events at any location. To make these changes easier to
  see, click on the 'Size' box within the Marks card; this will allow you to alter the size of each point within the
  map. Do so by dragging the Mark Size to the right. Making this change may
  be able to help us determine which council districts have the most marijuana related incidents.
- You can also see that there are now two keys next to our map on the right side of the visualization window, one for
  council district which is shown by color, and one for the number of incidents reported which is shown by size. This
  can also help provide additional context to the graph.
- Label and save your sheet.

### Exercise 6: Opening a Dashboard

Dashboards are a great way to showcase your results to the public or to do more complex analysis across
visualizations. In the Dashboard frame, you can showcase multiple visualizations at once.

To open a new dashboard:

- Select 'New Dashboard' icon
- In the 'Objects' section at the bottom left, select 'Floating' (instead of 'Tiled'), so that everything you add
  stays where you drop it
- Add your four sheets (the table, the bar chart, the line graph and the map) to the visualization pane by dragging
  them from the sheets menu
- Move each box by dragging it, and resize it by dragging its edges or corners, so that the sheets don't overlap
- Each sheet's keys come in floating too. Drag each key next to the visualization it belongs to

To help with analysis in the Dashboard frame, you can set it so one graph can control what information is shown in
the other. This can be done by setting one graph as the 'Filter' for the whole Dashboard.

- Select table sheet within the main Dashboard screen. On the right hand side of the visualization, select 'use as
  filter'
- Try selecting different age groups from the table to see the map change shape.

### Exercise 7 (optional): Enhancing visualization

If time is tight, skip to Exercise 8. You will want these features for Project 2, so come back to them later.

- **Titles:** Give each visualization a title that tells your audience what it shows. Right click on the sheet's tab at
  the bottom of the window and rename it; the title at the top of your visualization changes too. You can also double
  click on the title itself to edit it.
- **Tool Tip:** When you hover over a point of data, a small square of information pops up. In Tableau, this is called
  the Tool Tip. To edit it, click on the 'Tool Tip' card within the 'Marks' card. In the 'Edit Tool Tip' box, you can
  type any text you want, delete the greyed out &lt;variable name&gt; fields you don't need, and re-add fields from the
  'Insert' drop down.
- **Annotations:** An annotation is a note that stays visible on your graph, even in print, to draw attention to a
  point. Right click on the point you wish to draw attention to, select 'Annotate' and then 'Point', write something,
  and click OK.

### Exercise 8: Saving your work

There are several ways to save your work in Tableau. In Tableau Public, we save our work by publishing it to our
Tableau Public profile, which will enable us to work on our graphs in Tableau at a later date. However, if we want to
share our graphs, it might also be helpful save it as a .png.

- Click 'Download' on the toolbar and select 'Image'.

To upload your visualizations from your workbook to the internet:

- Click 'Publish As...' at the top right of the window
- Type a name for the workbook and click Publish
- After that, click 'Publish' whenever you want to save your changes
- To see your online graphic, click the X at the top right of the window

---

# Part 2 · Embedding a Tableau Visualization

Follow the steps below to find your Tableau URL, then embed it using either Option 1 (HTML) or Option 2 (Observable).
The two starter files, `tableau-embed.html` and `tableau-notebook.ojs`, are in this folder.

## Before You Begin: Get Your Tableau URL

Complete these steps first. You should have just created a Tableau visualization after following the tutorial in class!

In this lab, you will need your **Tableau viz URL** before filling out either template.

### PRE-STEP 1 — Publish your viz

- You should have already created your visualization in **Tableau Public**
- Make sure you published it to **Tableau Public**
- Make sure it is shared publicly (or with the appropriate permissions).

### PRE-STEP 2 — Copy your viz URL

- Open the published viz on Tableau Public.
- Click **Share** and copy the **Link** (not the embed code).
- Your URL will look like:

```
https://public.tableau.com/views/YOUR_WORKBOOK_NAME/YOUR_SHEET_NAME
```

📷 ![where to find link](images/share-link.png)

> **Keep this URL handy** — you will paste it into the code in both options below.

---

## Option 1: HTML file (`tableau-embed.html`)

Open `tableau-embed.html` in **VSCode** and fill in each marked step.

### STEP 1 — Add the Tableau viz container

Inside `<body>`, paste the code below. Replace `YOUR_TABLEAU_URL` with the URL you copied in Pre-Step 2.

```html
<tableau-viz
  id="tableauViz"
  src="YOUR_TABLEAU_URL"
  width="100%"
  height="800px">
</tableau-viz>
```

### STEP 2 — Set the viz size

Inside `<head>`, paste:

```html
<style>
  #tableauViz {
    width: 100%;
    height: 800px;
  }
</style>
```

### STEP 3 — Load the Tableau Embedding API

After the `<tableau-viz>` element, paste:

```html
<script type="module"
  src="https://public.tableau.com/javascripts/api/tableau.embedding.3.latest.min.js">
</script>
```

**Done.** Open the file in a browser to run it.

---

## Option 2: Observable Notebook (`tableau-notebook.ojs`)

Open `tableau-notebook.ojs`. Each block is a separate cell in Observable.
Go to [observablehq.com](https://observablehq.com), create a new notebook, and add one cell per step. Cells 2 and 3
are HTML: before pasting, click the small **ts** label at the cell's top right and choose **HTML**.

### CELL 1 — Load the Tableau Embedding API

```js
import("https://public.tableau.com/javascripts/api/tableau.embedding.3.latest.min.js");
```

### CELL 2 — Viz size

```html
<style>
  tableau-viz {
    width: 100%;
    height: 800px;
  }
</style>
```

### CELL 3 — Tableau viz container

Replace `YOUR_TABLEAU_URL` with the URL you copied in Pre-Step 2.

**Important: Ensure you have deleted all tracking parameters from your URL so it ends cleanly with your dashboard
name. Remove everything from the ? onward.**

**Example of link:**

Before:
https://public.tableau.com/views/Lab3_17611071284150/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

After:
https://public.tableau.com/views/Lab3_17611071284150/Dashboard1

```html
<tableau-viz
  src="YOUR_TABLEAU_URL"
  width="100%"
  height="800px">
</tableau-viz>
```

**Done.** The viz renders live inside the Observable notebook.

---

## Notes

- The viz must be published publicly, or the viewer must have Tableau Cloud/Server access.
- Interactive features — filtering, tooltips, and highlighting — remain available when embedded.
- The Tableau Embedding API v3 is the current standard; it uses a custom HTML element (`<tableau-viz>`) loaded via an
  ES module script.

---

# Submission

On Canvas, submit:

1. The link to your published **Tableau Public** dashboard (the URL from Pre-Step 2).
2. Your embed from Part 2:
   - **Option 2:** the link to your Observable notebook. Set it to **Unlisted** first (the globe icon in the
     notebook's sidebar), so we can open it.
   - **Option 1:** your `tableau-embed.html` file.

Full marks are for participating and finishing. If something broke and you could not fix it, say so and show us what
you tried.

Please take the remaining time in the workshop to explore changes to the graphs we have already made, including changing labels,
grouping variables, or changing effects with the options in your 'Marks Card'.

If you have any additional questions or wish to attend office hours to receive additional support with visualization
you made today or for a project, please email the TA: peidid@andrew.cmu.edu.
