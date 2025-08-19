# Agile planning and portfolio management with Azure Boards

## Lab requirements
This lab requires Microsoft Edge or an Azure DevOps supported browser.

Set up an Azure DevOps organization: If you don’t already have an Azure DevOps organization that you can use for this lab, create one by following the instructions available at [Create an organization or project collection](https://learn.microsoft.com/en-us/azure/devops/organizations/accounts/create-organization).

---

## Lab overview
In this lab, you’ll learn about the agile planning and portfolio management tools and processes provided by Azure Boards and how they can help you quickly plan, manage, and track work across your entire team. You’ll explore the product backlog, sprint backlog, and task boards that can track the flow of work during an iteration. We’ll also look at the enhanced tools in this release to scale for larger teams and organizations.

### Objectives
After you complete this lab, you will be able to:

- Manage teams, areas, and iterations.  
- Manage work items.  
- Manage sprints and capacity.  
- Customize Kanban boards.  
- Define dashboards.  
- Customize team process.  

**Estimated timing: 60 minutes**

---

## Instructions

### Exercise 0: (skip if done) Configure the lab prerequisites
In this exercise, you will set up the prerequisites for the lab, which consist of a new Azure DevOps project with a repository based on the eShopOnWeb.

#### Task 1: (skip if done) Create and configure the team project
In this task, you will create an eShopOnWeb Azure DevOps project to be used by several labs.

1. On your lab computer, in a browser window open your Azure DevOps organization.  
2. Click on **New Project**. Give your project the name **eShopOnWeb**. Define **Private** as Visibility option.  
3. Click **Advanced** and specify **Scrum** as Work Item Process.  
4. Click on **Create**.  

![Create new project panel](./images/create-new-project.png)

---

### Exercise 1: Manage Agile project
In this exercise, you will use Azure Boards to perform a number of common agile planning and portfolio management tasks, including management of teams, areas, iterations, work items, sprints and capacity, customizing Kanban boards, defining dashboards, and customizing team processes.

#### Task 1: Manage teams, areas, and iterations
In this task, you will create a new team and configure its area and iterations.

Each new project is configured with a default team, which name matches the project name. You have the option of creating additional teams. Each team can be granted access to a suite of Agile tools and team assets. The ability to create multiple teams gives you the flexibility to choose the proper balance between autonomy and collaboration across the enterprise.

- On your lab computer, start a web browser and navigate to the [Azure DevOps portal](https://aex.dev.azure.com).  
- Note: If prompted, sign in using the Microsoft account associated with your Azure DevOps subscription.  
- Open the **eShopOnWeb** project under your Azure DevOps organization.  

![Azure DevOps settings page](./images/settings-page.png)

- In the **General** section, select the **Teams** tab. There is already a default team in this project, *eShopOnWeb Team* but you’ll create a new one for this lab.  
- Click **New Team**.  

![Teams project settings window](./images/teams-settings.png)

- On the Create a new team pane, in the **Team name** textbox, type **EShop-Web**, leave other settings with their default values, and click **Create**.  

![Project settings teams page](./images/project-teams.png)

- In the list of Teams, select the newly created team to view its details.  
- Click **Iterations and Area Paths** link at the top of the EShop-Web page to start defining the schedule and scope of the team.  

![Iterations and Area Paths option](./images/iterations-areas.png)

- At the top of the Boards pane, select the **Iterations** tab and then click **+ Select iteration(s)**.  

![Iterations configuration page](./images/iterations-config.png)

- Select **eShopOnWeb\Sprint 1** and click **Save and close**.  
- Select **Sprint 1** and click the ellipsis (…). From the context menu, select **Edit**.  

![Iterations tab edit settings](./images/iterations-edit.png)

- Repeat the previous step to add **Sprint 2** and **Sprint 3**.  

![Sprints configuration under iterations tab](./images/sprints-config.png)

- Still in the Project Settings / Boards / Team Configuration pane, select the **Areas** tab.  

![Areas settings page](./images/areas-settings.png)

- Click the ellipsis (…) next to the default area entry and select **Include sub areas**.  

![Include sub areas option](./images/include-subareas.png)

---

#### Task 2: Manage work items
In this task, you will step through common work item management tasks.

- Click on the project name in the upper left corner of the Azure DevOps portal to return to the project home page.  
- In the vertical navigational pane of the Azure DevOps portal, select **Boards > Work Items**.  
- On the Work Items window, click on **+ New Work Item > Epic**.  

![Work item creation](./images/workitem-create.png)

- In the **Enter title** textbox, type **Product training**.  
- Assign it to yourself, set **Area** to *eShopOnWeb\EShop-WEB*, and set **Iteration** to *eShopOnWeb\Sprint 2*.  
- Click **Save**.  

![Work item details](./images/workitem-details.png)

- In the **Related work** section, select **Add link > New item**.  
- Set **Link Type** = Child, **Work item type** = Feature, **Title** = Training dashboard.  

![Work item link creation](./images/workitem-link.png)

- Save and close the feature.  

![Work item related work area](./images/workitem-related.png)

- Navigate to **Boards > EShop-WEB boards**.  

![EShop-WEB board selection](./images/board-selection.png)

- On the Boards panel, switch to **Features**.  
- Add PBIs under the Training dashboard feature:  
  - As a customer, I want to view new tutorials  
  - As a customer, I want to see tutorials I recently viewed  
  - As a customer, I want to request new tutorials  

![Add Product Backlog Item](./images/add-pbi.png)

---


On the Boards panel, in the upper right corner, select the Features entry and, in the dropdown list, select Backlog items.

![View backlog items](./images/view-backlog-items.png)

Note: Backlog items have a state that defines where they are relative to being completed. While you could open and edit the work item using the form, it’s easier to just drag cards on the board.

On the Board tab of the EShop-WEB panel, drag the first work item named **As a customer, I want to view new tutorials** from the New to Approved stage.

![Board with work items](./images/board-workitems.png)

Note: You can also expand work item cards to get to conveniently editable details.

Hover with the mouse pointer over the rectangle representing the work item you moved to the Approved stage. This will reveal the down facing caret symbol.  
Click the down facing caret symbol to expand the work item card, replace the Unassigned entry with your name, then select your account to assign the moved PBI to yourself.  
On the Board tab of the EShop-WEB panel, drag the second work item named **As a customer, I want to see tutorials I recently viewed** from the New to the Committed stage.  
On the Board tab of the EShop-WEB panel, drag the third work item named **As a customer, I want to request new tutorials** from the New to the Done stage.  

![Board with moved work items](./images/board-moved.png)

---

Note: The task board is one view into the backlog. You can also use the tabular view.

On the Board tab of the EShop-WEB pane, at the top of the pane, click **View as Backlog** to display the tabular form.

![EShop-WEB backlog](./images/backlog-view.png)

Note: You can use the plus sign directly under the Backlog tab label of the EShop-WEB panel to view nested tasks under these work items.  
Note: You can use the second plus sign directly left to the first backlog item to add a new task to it.  

On the Backlog tab of the EShop-WEB pane, in the upper left corner of the pane, click the plus sign next to the first work item. This will display the NEW TASK panel.  

![Create task option](./images/create-task.png)

- Enter title: **Add page for most recent tutorials**  
- Remaining Work: **5**  
- Activity: **Development**  
- Click **Save and Close**  

![New work item creation](./images/new-task.png)

Repeat the last five steps to add another task named **Optimize data query for most recent tutorials**.  
Set Remaining Work = **3** and Activity = **Design**.  

---

### Task 3: Manage sprints and capacity

Teams build the sprint backlog during the sprint planning meeting, typically held on the first day of the sprint. Each sprint corresponds to a time-boxed interval which supports the team’s ability to work using Agile processes and tools.

... (content continues with screenshots and notes about sprints, capacity, board customization, Kanban boards, and dashboards as in the instructions) ...



On the Configure Chart panel, in the Name textbox, type **Web tasks - By assignment**, in the Group by dropdown list, select **Assigned To**, and click **Save chart** to save the changes.

![Web tasks pie chart](./images/webtasks-piechart.png)

Note: You can now add this chart to a dashboard.

Return to the Dashboards section in the Overview Menu. From the EShop-Web section, select the **Product Training** dashboard you used earlier, to open it.

- Click **Edit** from the top menu.  
- From the **Add Widget** list, search for **Chart**, and select **Chart for Work Items**.  
- Click **Add** to add this widget to the EShop-Web dashboard.  

Click the configure (cogwheel) within the **Chart for Work Items** to open the widget settings.

- Accept the title as is.  
- Under Query, select **Shared Queries / Web Tasks**.  
- Keep **Pie** for Chart Type.  
- Under Group By, select **Assigned To**.  
- Keep the Aggregation (**Count**) and Sort (**Value / Ascending**) defaults.  

Confirm the configuration by clicking **Save**.

Notice the query results pie chart is shown on the dashboard. Save the changes by pressing the **Done Editing** button on top.

---

## Review

In this lab you used Azure Boards to perform a number of common agile planning and portfolio management tasks, including management of teams, areas, iterations, work items, sprints and capacity, customizing Kanban boards, and defining dashboards.

