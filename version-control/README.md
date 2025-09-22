# Version Control with Git in Azure Repos

## Lab Requirements
- Microsoft Edge or any Azure DevOps supported browser.  
- Azure DevOps organization (create one if you don’t already have it).
- Git 2.47.0 or later → [Git for Windows](https://gitforwindows.org/).  
- Visual Studio Code → [Download VS Code](https://code.visualstudio.com/).  
- Visual Studio Code C# extension → [Download C# Extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## Lab Overview
Azure DevOps supports **Git** (distributed) and **TFVC** (centralized). Git is the default and recommended option.

In this lab, you will:  
- Establish a local Git repository synced with Azure DevOps.  
- Learn Git branching and merging using Visual Studio Code.  
- Explore commits, history, branches, pull requests, and tags.

**Estimated time:** 45 minutes

## Objectives
- Clone an existing repository.  
- Save work with commits.  
- Review history of changes.  
- Work with branches using Visual Studio Code.

---

## Exercise 0: Configure Prerequisites

### Task 1: Configure Git and Visual Studio Code
1. Open **Visual Studio Code**.  
2. Go to **Terminal → New Terminal** (ensure it shows *PowerShell*).  
   - To change shell → dropdown → *Select Default Shell* → Windows PowerShell → `+` to open new terminal.
3. Configure Git credentials:
   ```bash
   git config --global credential.helper wincred
   git config --global user.name "<Your Name>"
   git config --global user.email <your@email.com>
   ```

### Task 2: Create Azure DevOps Project (skip if already done)
1. Go to **Azure DevOps Organization → New Project**.  
2. Name: `eShopOnWeb`.  
3. Work Item Process: **Scrum** → **Create**.

### Task 3: Import eShopOnWeb Repository (skip if already done)
1. Go to **Azure DevOps → eShopOnWeb Project → Repos → Files → Import**.  
2. URL: `https://github.com/MicrosoftLearning/eShopOnWeb.git` → **Import**.

Repository structure:  
- `.ado` → YAML pipelines  
- `.devcontainer` → container setup  
- `infra` → IaC templates  
- `.github` → GitHub workflows  
- `src` → .NET 8 website

### Task 4: Set Default Branch
1. Go to **Repos → Branches**.  
2. Hover **main** → Ellipsis (…) → **Set as default branch**.

---

## Exercise 1: Clone an Existing Repository

### Task 1: Clone Repository
1. In **Azure DevOps → Repos → eShopOnWeb → Clone**.  
2. Copy **HTTPS clone URL**.  
3. In **VS Code → View → Command Palette** → type `Git: Clone`.  
4. Paste the URL → choose folder `C:\Git` → **Select as Repository Destination**.  
5. Sign in if prompted → **Open** repo in VS Code.

---

## Exercise 2: Save Work with Commits

### Task 1: Commit Changes
1. In **VS Code → Explorer → src/Web/Program.cs**, add:
   ```csharp
   // My first change
   ```
2. Save file (`Ctrl+S`).  
3. Go to **Source Control tab** → Enter message `My commit` → `Ctrl+Enter`.  
4. If prompted, stage automatically.  
5. Click **Sync Changes** (↕ icon) to push.

### Task 2: Review Commits in Azure DevOps
- Go to **Repos → Commits** → Confirm commit appears.

### Task 3: Stage Changes
1. Modify `Program.cs`:
   ```csharp
   // My second change
   ```
2. Modify `Constants.cs`:
   ```csharp
   // My third change
   ```
3. In **Source Control tab** → Hover `Program.cs` → `+` to stage.  
4. Message: `Added comments` → Ellipsis (…) → **Commit → Commit Staged**.  
5. Click **Sync Changes**.

---

## Exercise 3: Review History

### Task 1: Compare Files
1. In **VS Code → Source Control tab**, open `Constants.cs` to view changes.  
2. In **Azure DevOps → Repos → Commits** → Ellipsis (…) → **Browse Files** to review source.

---

## Exercise 4: Work with Branches

### Task 1: Create New Branch
1. In **VS Code → Source Control tab → Bottom Left → main** → **+ Create new branch**.  
2. Base: **main**.  
3. Name: `dev`.  
4. You are switched to `dev` branch.

### Task 2: Delete Branch
1. In **VS Code → Publish changes** for `dev`.  
2. In **Azure DevOps → Repos → Branches → Mine** → Hover `dev` → Ellipsis (…) → **Delete branch**.  
3. Go to **Branches → All** → Search `dev` → **Restore branch**.

### Task 3: Apply Branch Policies
1. In **Azure DevOps → Repos → Branches → main → Ellipsis (…) → Branch Policies**.  
2. Enable:
   - **Require minimum reviewers** → 1 (allow requestors to approve).  
   - **Check for linked work items** → Required.

### Task 4: Test Branch Policy
1. In **Repos → Files → main → src/Web/Program.cs**, add:
   ```csharp
   // Testing main branch policy
   ```
2. Try **Commit** → Warning: only Pull Request allowed → Cancel.

### Task 5: Create Pull Request
1. In **Boards → Work Items → + New Work Item → Product Backlog Item** → Title: *Testing my first PR* → Save.  
2. In **Repos → Files → dev → src/Web/Program.cs**, add:
   ```csharp
   // Testing my first PR
   ```
3. Commit.  
4. Popup: **Create Pull Request** → Create.  
5. Link the Work Item → Approve → Complete → Merge (no fast-forward).  
6. Check **Complete associated work item** → Complete Merge.

### Task 6: Apply Tags
1. In **Repos → Tags → New Tag**.  
2. Name: `v1.1.0-beta` → Based on `main` → Description: *Beta release v1.1.0* → **Create**.

---

## Exercise 5: Remove Branch Policies
1. In **Repos → Branches → Mine → main → Ellipsis (…) → Branch Policies**.  
2. Disable:
   - Require minimum number of reviewers.  
   - Check for linked work items.

---

## Review
In this lab, you:
- Configured Git and VS Code.  
- Imported and cloned a repo.  
- Committed and staged changes.  
- Reviewed history.  
- Created and managed branches.  
- Applied and tested branch policies.  
- Worked with pull requests.  
- Applied tags.  
- Removed branch policies.