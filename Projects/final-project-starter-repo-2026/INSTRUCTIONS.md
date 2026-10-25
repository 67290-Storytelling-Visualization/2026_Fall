# 67-290 Final Project Instructions

The final project for 67-290 centers around creating a dashboard with visualizations and a final report, implemented in phases to guide you. The dashboard should tell a central story about a specified social issue with the data, aiming to impact through visualizations.

See [timeline.md](./timeline.md) for the full phase schedule at a glance.

---

## Phase Overview and Submission Deliverables

*Absolutely no late submissions will be accepted for credit unless extenuating circumstances arise in accordance with the course syllabus.*

### Phase 1: Proposal and Wireframing

In this phase, you will submit a formal proposal for your project. Your proposal must include the following six sections, in this order, each as its own subheading:

1. **Issue** — the social issue you plan to explore. Why is it significant? What message do you want to convey to your audience?
2. **Problem** — what problems do you want to find answers to, or make an argument for?
3. **Purpose** — the purpose of your visualization and storytelling.
4. **Stakeholders** — your target audience and the impact you aim to achieve.
5. **Data Sources** — the datasets you plan to use, and why they're relevant, reliable, and ethical.
6. **Initial Visualization Charts** — for your story's purpose, what visualization charts will you use, how will you apply visual encoding elements/principles to them, and why?

You can use a wireframe if you think it helps to express your design ideas (optional).

**Phase Deliverables**

- Formal Proposal (Brief 1-2 pages, all six sections above in order)
- Wireframe (optional, can be embedded in the same document)

***Submit the deliverables to Canvas by 11:59PM on Monday, November 16, 2026.***

#### Quick Tips for Wireframing

- You can use tools like [Balsamiq](https://balsamiq.com) for lo-fi wireframing.
- Focus on the big picture. Do not get too caught up in the small details and focus on creating a layout with an intuitive user flow for your dashboards.
- Think about how the various dashboards will flow together to make up the larger story you are trying to tell.
- Review your design principles so you can apply them to create great dashboards!

### Phase 2: Midpoint Check

This phase checks four specific, boundable things rather than asking for a full dashboard, so workload splits evenly across your team:

1. **One dashboard page live**, addressing one goal/question from your Phase 1 proposal, pushed to your team repository and deployed to Vercel (as done in previous labs) so we can view it live.
2. **Visualization principles applied and named** — in your interim report, state which principles you used (visual encoding, Gestalt principles, data-ink ratio, avoiding chart junk, small multiples) and where.
3. **At least one annotation or illustration** on the dashboard that guides the viewer toward your story's key point.
4. **Contribution log**: fill out [CONTRIBUTIONS.md](./CONTRIBUTIONS.md) in your repository, logging each member's contributions (code and non-code) as you work. This is not graded on "who did more," it exists so uneven workload is visible now instead of at the end.

Note: You can use JavaScript, ArcGIS, and/or Tableau as your visualizations within this dashboard. Instructions on embedding finished visualizations from ArcGIS and Tableau can be found below in the "Helpful Resources" section.

**Phase Deliverables**

- Your GitHub repository URL (Make sure to add `peidid` as a collaborator so we can grade your project)
- Deployed dashboard URL (Vercel)
- Interim report (refined Phase 1 proposal, with the named principles from item 2 above)
- Contribution log: fill out [CONTRIBUTIONS.md](./CONTRIBUTIONS.md) in your repository, logging each member's contributions (code and non-code) as you work

***Submit the deliverables to Canvas by 11:59PM on Monday, November 23, 2026.***

### Phase 3: Final Project Dashboard and Final Report

In this phase, your team will create the dashboard(s) for the remaining goal(s) outlined in your project proposal and then push them to the team's repository, keeping your Vercel deployment up to date.

**Phase Deliverables**

- GitHub repository URL
- Deployed dashboard URL (Vercel)
- Final Project Report
- Presentation (.pptx or .pdf format)
- Peer evaluation filled out in the provided Google form

***Submit the deliverables to Canvas by 11:59PM on Sunday, November 29, 2026.***

### Phase 4: Final Project Presentation & Peer Team Evaluations

On presentation day, present your visualization dashboard to the class, explaining the social issue, the story you aimed to convey, your arguments, and the visualization choices you made. You will fill out an evaluation of your fellow students' projects during the final project presentations.

**Phase Deliverables**

- Final project presentation in class on Monday, November 30, 2026 (last day of class). You will fill out the Final Project Peer Team Evaluation form during the presentation.

---

## Navigating the Starter Code

We have provided you with starter code at https://github.com/67290-Storytelling-Visualization/2026_Fall/tree/main/Projects/final-project-starter-repo-2026

The starter code is for a dashboard in Observable Framework. Here is how to get started (only **ONE** person in your team needs to do this):

1. Clone the course repository and copy the `Projects/final-project-starter-repo-2026` folder to a new folder for your project.
2. Inside that new folder, start a new repository with `git init`.
3. Create a new (private) repository on GitHub. Add your other partners and `peidid` as collaborators to the repository.
4. Add a link to the newly created remote repository with `git remote add origin [your-repository-url-here]`.

### Observable Dashboards 101

***Do not delete or rename `index.md`! This should be kept as your home page.***

**Extensions of files:**

- `.md` files are for pages, written in Markdown and HTML with embedded code (typically JavaScript).
- `.json.js` files are for data loaders written in JavaScript that return a JSON.
- `.js` files are typically component files written in JavaScript that contain visualizations.

**Pages:**

- You can directly use Markdown or HTML syntax in `.md` files for pages.
- You need to place any JavaScript code in JS cells/code blocks indicated by triple ticks ```.
- Remember that grids, cards, table of contents, and themes are built in (among other awesome UI/UX components).

**Data Loaders:**

- Ensure you are using the correct extensions for your data loaders! It should be the format of the output followed by the language the data loader is written in.

> Examples:
>
> 1. Python data loader with output of csv: `file.csv.py`
> 2. Python data loader with output of json: `file.json.py`
> 3. JavaScript data loader with output of csv: `file.csv.js`
> 4. JavaScript data loader with output of json: `file.json.js`

**Components:**

- Modularize your code by separating components into JavaScript files in the `components` folder and importing them into pages.

**Creating a Report in Observable:**

- Just type your report using Markdown syntax.
- Insert JS cells/code blocks where you want to embed your visualizations within your report.
- You should include the table of contents on the report page by setting `toc` to `true`.
- Refer to `example-report.md` if you are still confused.

**Anatomy of a Report in Observable**

![Anatomy of a Report in Observable](https://i.imgur.com/JRZsGBx.png)

---

## Coding Advice for the Project

- First and foremost, ***START EARLY!!!!!***

- **Plan thoroughly** before touching any code!!! Work with your team to figure out what components and files need to be completed for each goal/dashboard. This will make it much easier to sit down and code. Coding with a plan is always more efficient!

> **Code Planning 101!**
>
> *Ask these questions when planning (in this order):*
>
> 1. What features do I need to address this goal/question?
> 2. What are the different parts/components I need to create this feature?
> 3. What are the different files I need to create the different parts?
> 4. What major functions or other coding structures should I include in each file?

- Don't work on **overlapping/dependent features**. Try to divide the work so that it does not overlap and is independent of each other's progress. Parallel work is key to efficient and rapid progress!

> **Overlapping example**: Working on the same page. This is fine if you are each working in different files, such as creating separate and independent components. We suggest creating a shared file for the report page (as completing this should be a joint effort!) that updates in real time (such as a Google Doc) and delegating updating the repository with the information to one partner.
>
> **Dependency example**: Working on a feature dependent on another person's work. If there are two components and one data loader for each component, we suggest splitting up the work such that each person works on one component with its corresponding data loader rather than one person working on the data loaders and the other working on the components. By doing so, neither partner's progress will be hindered or dependent on the other's.

- Create and push to **separate feature branches**. This keeps your work off the main branch until it is fully ready and gives your partner the chance to review your changes before merging them into the main branch (make pull requests!). This also has the added benefit of allowing you to just delete a branch if it is beyond saving and start anew.

> **A Quick Tutorial of Using, Pushing, and Merging Feature Branches!**
>
> 1. Create a feature branch locally with `git checkout -b "feature-branch-name"`
> 2. When you are ready to push your changes from the feature branch to the remote repository, use `git push --set-upstream origin feature-branch-name`. This will push your changes to the remote version of your feature branch rather than the remote `main` branch.
> 3. Go to your feature branch on GitHub (in the remote repository). Under the branch dropdown below the title of your repository, click on your feature branch.
> 4. Click on the button that says **"Compare and pull request"**.
> 5. Now make a pull request and request one of your teammates as a reviewer under Reviewers. Your teammate should do a code review before you merge code into the main branch.
> 6. Once everything looks good to both you and your team, click the **"Merge pull request"** button in the pull request. This should merge it into main if there are no conflicts.

- Try as much as possible to **work together in person**. Joint coding/debugging sessions in person are much more effective and you will get more done. Setting up an agenda/to-do list to address during work sessions can be very helpful to keep you on track and less distracted.

- **Take breaks** and ask your team for help when debugging. Debugging can take a long time and fresh eyes are much more effective at spotting bugs. That is, take breaks in between coding and debugging to keep your eyes fresh and ask your team to take a quick glance at your code if you are *really* stuck.

- Last but not least: ***START EARLY!!!!!*** **Seriously - Please. Start. Early.**

---

## Helpful Resources for the Project

*This is a centralized area with some helpful resources we have compiled to help you get started. This is **by no means a comprehensive list** of resources and we expect you to do some searching of your own in order to meet your specific needs for your project. We have focused **primarily** on resources compatible with what we have touched on in class and assignments, but **by all means feel free to explore and use other resources**. Please keep in mind that support for resources other than the ones touched on in class will be limited, as course staff will try their best to help you with them but they may not be familiar to course staff.*

### How to Integrate Visualizations within Observable Dashboards (JavaScript)

- [Instructions for Embedding ArcGIS in Observable](https://doc.arcgis.com/en/arcgis-online/share-maps/embed-maps-groups.htm)
- [Instructions for Embedding Story Maps in Observable](https://www.esri.com/arcgis-blog/products/arcgis-online/mapping/embedding-story-maps-in-websites-and-blogs)
- [Instructions for Embedding Tableau in Observable](https://help.tableau.com/current/pro/desktop/en-us/embed.htm)

### API Sources

- [PublicAPIs](https://publicapis.dev)
- [Public APIs](https://github.com/toddmotto/public-apis)
- [Public API Lists](https://github.com/public-api-lists/public-api-lists)
- [Rapid API](https://rapidapi.com/hub)
- [Free Public APIs](https://www.freepublicapis.com)

### Static Data Sources

*Tip: Depending on what you are looking for, government agencies and other large bureaucratic organizations have rich sources of open data you can use.*

- [Google Dataset Search](https://datasetsearch.research.google.com)
- [Kaggle](https://www.kaggle.com/datasets)
- [US Census Data](https://data.census.gov)
- [US Government Open Data](https://data.gov)
- [Pew Research Center](https://www.pewresearch.org/internet/datasets)

### Dashboards

- Observable Framework (JavaScript): https://observablehq.com/framework

### Visualization Libraries/Tools

- [Curated list of open-source data visualization frameworks, libraries, and software](https://github.com/hal9ai/awesome-dataviz)
- [Observable Plot](https://observablehq.com/plot)
- [ArcGIS documentation](https://www.esri.com/en-us/arcgis/products/arcgis-pro/resources) (scroll down to **Documentation**)
- [Tableau: Connect To and Prepare Data](https://help.tableau.com/current/pro/desktop/en-us/data.htm)
- [Tableau: Build Charts and Design Data](https://help.tableau.com/current/pro/desktop/en-us/design_and_analyze.htm)
- [Tableau Public beginner's guide](https://www.tableau.com/blog/beginners-guide-tableau-public)
- [Observable Framework libraries](https://observablehq.com/framework) (use **Libraries** in the sidebar)
