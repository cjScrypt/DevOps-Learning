# Version Control with Git in Azure Repos

## Lab requirements
This lab requires Microsoft Edge or an Azure DevOps supported browser.

- **Set up an Azure DevOps organization**: If you don’t already have an Azure DevOps organization that you can use for this lab, create one by following the instructions available at [Create an organization or project collection](https://learn.microsoft.com/azure/devops/organizations/accounts/create-organization).

- **Install prerequisites**:
  - [Download Git](https://git-scm.com/download/win) (version 2.47.0 or later).
  - [Download Visual Studio Code](https://code.visualstudio.com/download).
  - [Install C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

---

## Lab overview
Azure DevOps supports two types of version control:

- **Team Foundation Version Control (TFVC)**: A centralized version control system where history is kept only on the server.
- **Git**: A distributed version control system where developers keep a local copy of the repository.

Git is the default provider for new projects. You’ll establish a local Git repository, sync it with Azure DevOps, and explore Git branching and merging using Visual Studio Code.

---

## Objectives
After completing this lab, you will be able to:

- Clone an existing repository.
- Save work with commits.
- Review history of changes.
- Work with branches using Visual Studio Code.

**Estimated timing: 45 minutes**

---

## Instructions

### Exercise 0: Configure the lab prerequisites

#### Task 1: Configure Git and Visual Studio Code

```bash
git config --global credential.helper wincred
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

#### Task 2: (skip if done) Create and configure the team project

1. Open your Azure DevOps organization → **New Project** → Name: `eShopOnWeb` → Process: `Scrum` → **Create**.

![Create new project panel](./images/create-project.png)

#### Task 3: (skip if done) Import eShopOnWeb Git Repository

1. Open `Repos > Files` → **Import**.
2. Paste URL: `https://github.com/MicrosoftLearning/eShopOnWeb.git` → **Import**.

![Import repository panel](./images/import-repo.png)

#### Task 4: (skip if done) Set main branch as default branch

1. Go to `Repos > Branches` → Hover `main` → **Set as default branch**.

---

### Exercise 1: Clone an existing repository

1. In Azure DevOps, go to **Repos → Clone** → Copy HTTPS URL.
2. In VS Code → **Command Palette (Ctrl+Shift+P)** → `Git: Clone` → Paste URL → Select folder (`C:\Git`).

![Clone Git repository](./images/clone-repo.png)

---

### Exercise 2: Save work with commits

#### Task 1: Commit changes

1. Open `src/Web/Program.cs` → Add:

```csharp
// My first change
```

2. Save → Go to **Source Control** → Commit message: `My commit` → **Commit & Sync**.

![First commit](./images/first-commit.png)

#### Task 3: Stage changes

1. Modify `Program.cs`:

```csharp
// My second change
```

2. Modify `Constants.cs`:

```csharp
// My third change
```

3. Stage only `Program.cs` → Commit message: `Added comments` → **Commit Staged & Sync**.

![Staged changes](./images/staged-changes.png)

---

### Exercise 3: Review history

- Use **Azure DevOps → Repos → Commits** to review history.

![Commit history](./images/commit-history.png)

---

### Exercise 4: Work with branches

#### Task 1: Create a new branch

- In VS Code, bottom-left → `main` → **+ Create new branch from…** → Name: `dev`.

![Create branch](./images/create-branch.png)

#### Task 2: Delete & restore branch

- Delete `dev` branch in Azure DevOps.
- Restore from **Deleted branches**.

![Restore branch](./images/restore-branch.png)

#### Task 3: Branch Policies

1. Go to `Branches` → Ellipsis on `main` → **Branch Policies**.
2. Enable:
   - Require minimum 1 reviewer (allow self-approval).
   - Check for linked work items.

![Branch policies](./images/branch-policies.png)

#### Task 4: Test branch policy

- Make a change → Push → Create a **Pull Request** → Validate against policy.

---


---

In the **Create a tag** panel, in the **Name** text box, type `v1.1.0-beta`, in the **Based on** drop-down list leave the `main` entry selected, in the **Description** text box, type `Beta release v1.1.0` and click **Create**.

> **Note**: You have now tagged the repository at this release (the latest commit gets linked to the tag). You could tag commits for a variety of reasons and Azure DevOps offers the flexibility to edit and delete them, as well as manage their permissions.

---

## Exercise 5: Remove Branch Policies

When going through the different course labs in the order they are presented, the branch policy configured during this lab will block exercises in future labs. Therefore, we want you to remove the configured branch policies.

1. From the **Azure DevOps eShopOnWeb Project view**, navigate to `Repos → Branches`.
2. Select the **Mine** tab of the Branches pane.
3. Hover over the `main` branch entry → Click the ellipsis (**...**) → Select **Branch Policies**.

![Policy settings](./images/policy-settings.png)

4. Disable the option **Require minimum number of reviewers**.
5. Disable the option **Check for linked work items**.

![Branch policies](./images/branch-policies.png)

You have now disabled/removed the branch policies for the **main** branch.

---

## Review

In this lab, you have learned how to use **Git for version control in Azure Repos**.
