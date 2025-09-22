# **Agile Planning and Portfolio Management with Azure Boards**

## **Lab Requirements**
- Microsoft Edge or another Azure DevOps supported browser.
- An Azure DevOps organization. If you don’t have one, create it by following [Create an organization or project collection](https://learn.microsoft.com/azure/devops/organizations/accounts/create-organization).

## **Lab Overview**
In this lab, you will explore **Azure Boards** for agile planning and portfolio management. You’ll learn how to:
- Manage teams, areas, and iterations.
- Manage work items.
- Manage sprints and capacity.
- Customize Kanban boards.
- Define dashboards.
- Customize team process.

**Estimated time:** 60 minutes

---

## **Exercise 0: Configure Lab Prerequisites**
*(Skip if already completed)*

- Create an **eShopOnWeb** Azure DevOps project.
- Set **Visibility** to *Private*.
- Under **Advanced**, choose **Scrum** as the Work Item Process.

---

## **Exercise 1: Manage Agile Project**

### **Task 1: Manage Teams, Areas, and Iterations**
1. Go to your Azure DevOps organization → Open the **eShopOnWeb** project.
2. Navigate to **Project Settings → Teams → New Team** → Name it `EShop-Web` → Create.
3. Configure team:
   - **Iterations:** Project Settings → Teams → EShop-Web → Iterations and Area Paths → Iterations. Add three sprints (*Sprint 1*, *Sprint 2* and *Sprint 3*). Edit each sprint to set a 3-week duration. Make sure each new sprint begins immediately after the previous one ends.
   - **Areas:** Project Settings → Teams → EShop-Web → Areas → Set default to **Include sub-areas**.

### **Task 2: Manage Work Items**
1. Go to **Boards → Work Items → + New Work Item → Epic** → Title: *Product training*.
   - Assign to yourself.
   - Area Path: `eShopOnWeb\EShop-WEB`.
   - Iteration: `Sprint 2`.
   - Save.
2. Under **Related Work**, add **Child → Feature** → Title: *Training dashboard*.
3. Go to **Boards → Boards, select **EShop-Web**. Switch view to Features** and click **Add Product Backlog Items (PBIs)**:
   - *As a customer, I want to view new tutorials.*
   - *As a customer, I want to see tutorials I recently viewed.*
   - *As a customer, I want to request new tutorials.*
4. On the **Board** tab, drag *“As a customer, I want to view new tutorials”* from **New → Approved**.  
5. Hover over the card, click the down caret, and assign it to yourself by replacing *Unassigned* with your name.  
6. Drag *“As a customer, I want to see tutorials I recently viewed”* from **New → Committed**.  
7. Drag *“As a customer, I want to request new tutorials”* from **New → Done**.
8. Add **Tasks**:
   - Task: *Add page for most recent tutorials* (Remaining Work: 5, Activity: Development).
   - Task: *Optimize data query for most recent tutorials* (Remaining Work: 3, Activity: Design).

### **Task 3: Manage Sprints and Capacity**
1. Go to **Boards → Boards → Sprints → Taskboard**. Select **View options** and activate **Work details** side pane. Select *Sprint 2* as filter.
2. Assign tasks to yourself.
3. Go to **Capacity** tab:
   - Add Activity: *Development*, Capacity per day = 1 (Representing 1 hour of development work per day).
   - Add 5 days off during the current sprint.
   - Save.
4. Update estimated number of work hours for *Add page for most recent tutorials* to 9.
5. Switch to **View → Assigned To** for workload overview.
6. Customize sprint board:
   - **Board Settings → Styles** → Add rule (Activity = Development → green cards).
   - **Board Settings → General** →  Working days, Customize your team working day.

### **Task 4: Customize Kanban Boards**
1. Go to **Boards → Board Settings → Tag Colors** → Add tag *data* (yellow).
2. Add tags *data* and *ux* to backlog items.
3. **Boards → Board Settings → Columns**:
   - Add column *QA Approved* (WIP limit = 1) between *Committed* and *Done*.
   - Enable **Split columns** (*Doing/Done*).
   - Define **Definition of Done**: *Passes all tests*.
4. **Boards → Board Settings → Swimlanes** → Add *Expedite* (green). Move priority items here.

---

## **Exercise 2: Define Dashboards**

### **Task 1: Create and Customize Dashboards**
1. Go to **Overview → Dashboards → + New Dashboard** → Name: *Product Training*, Team: *EShop-Web*.
2. Add widgets:
   - **Sprint Overview**
   - **Sprint Capacity** → Configure: Activity = Development, Capacity = 1.
3. Go to **Boards → Queries → + New Query**:
   - Work Item Type = Task.
   - Area Path = `eShopOnWeb\EShop-WEB`.
   - Save as *Web tasks* under Shared Queries.
4. Go to **Boards → Queries → Charts → New Chart**:
   - Query: *Web tasks*.
   - Chart: *By assignment* (Group by Assigned To).
5. Go to **Overview → Dashboards → Product Training → Add Widget → Chart for Work Items** → Select *Web tasks - By assignment*.

---

## **Review**
In this lab, you used **Azure Boards** to:
- Manage teams, areas, iterations, work items, and sprints.
- Configure capacity and workloads.
- Customize Kanban boards with tags, WIP limits, and swimlanes.
- Define and customize dashboards with queries and widgets.
