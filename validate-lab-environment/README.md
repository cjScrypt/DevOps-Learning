# Validate Lab Environment

In preparation for the labs, it is crucial to have your environment correctly set up. This page will guide you through the setup process, ensuring all prerequisites are met.

The labs require Microsoft Edge or an Azure DevOps-supported browser.

## Prerequisites

- **Azure Subscription**: If you don’t already have an Azure subscription, create one by following the instructions on this page or visit [Azure Free](https://azure.microsoft.com/free).
- **Azure DevOps Organization**: If you don’t already have an Azure DevOps organization, create one by following the instructions on this page or at *Create an organization or project collection*.
- [Git for Windows](https://gitforwindows.org/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Azure CLI](https://learn.microsoft.com/cli/azure/install-azure-cli) – Install on the self-hosted agent machines.
- [.NET SDK (latest version)](https://dotnet.microsoft.com/download/visual-studio-sdks) – Install on the self-hosted agent machines.

---

## Instructions to Create an Azure DevOps Organization

> **Note**: Start at step 3 if you already have a personal Microsoft Account setup and an active Azure Subscription.

1. Use a private browser session to get a new personal Microsoft Account (MSA) at [account.microsoft.com](https://account.microsoft.com).
2. Using the same browser session, sign up for a free Azure subscription at [Azure Free](https://azure.microsoft.com/free).
3. Navigate to [Azure portal](https://portal.azure.com) and search for **Azure DevOps**.
4. Click **Azure DevOps organizations** and then **My Azure DevOps Organizations** or go to [aex.dev.azure.com](https://aex.dev.azure.com).
5. On the **We need a few more details** page, select **Continue**.
6. In the drop-down, choose **Default Directory** instead of Microsoft Account.
7. Provide your name, e-mail, and location if prompted, then click **Continue**.
8. At [aex.dev.azure.com](https://aex.dev.azure.com), select **Create new organization**.
9. Accept the Terms of Service and click **Continue**.
10. If prompted (“Almost done”), leave the default organization name and pick a hosting location close to you.
11. Once created, go to **Organization settings** → **Billing** and link your Azure Subscription.
12. Change **Paid parallel jobs for MS Hosted CI/CD** from `0` to `1` and click **Save**.
13. In **Organization Settings** → **Pipelines** → **Settings**, toggle:
    - `Disable creation of classic build pipelines` → **Off**
    - `Disable creation of classic release pipelines` → **Off**
14. In **Organization Settings** → **Security** → **Policies**, toggle:
    - `Allow public projects` → **On**

---

## Instructions to Create and Configure Azure DevOps Project

1. Open your Azure DevOps organization in the browser.
2. Create a **New Project** with the following settings:
   - Name: `eShopOnWeb`
   - Visibility: `Private`
   - Version Control: `Git`
   - Work Item Process: `Scrum`

   ![Create new project](./images/create-project.png)

### Import eShopOnWeb Git Repository

1. Navigate to the newly created `eShopOnWeb` project.
2. Go to **Repos > Files**, select **Import a Repository**, then click **Import**.
3. Use the URL:  
   `https://github.com/MicrosoftLearning/eShopOnWeb`

   ![Import repository](./images/import-repo.png)

4. The repository contains:
   - `.ado` → Azure DevOps YAML pipelines  
   - `.devcontainer` → Container setup for VS Code or GitHub Codespaces  
   - `.azure` → Bicep & ARM infrastructure templates  
   - `.github` → GitHub workflow YAML definitions  
   - `src` → .NET 8 website for lab scenarios  

5. Go to **Repos > Branches**, set **main** as the default branch.

---

## Create a Service Connection

1. Open [Azure DevOps portal](https://aex.dev.azure.com).
2. Open the `eShopOnWeb` project and go to **Project settings** → **Service connections** → **Create service connection**.

   ![New service connection](./images/new-service-connection.png)

3. On the New service connection blade:
   - Select **Azure Resource Manager**
   - Identity type: **App registration (automatic)**
   - Workload Identity federation: **On**
   - Scope level: **Subscription**

4. Fill in:
   - **Subscription**: Select your Azure subscription
   - **Resource group**: Choose or create a resource group
   - **Service connection name**: `azure subs`

   > ⚠️ Do **not** select *Grant access permission to all pipelines* (not recommended for production).

---

✅ You have now completed the prerequisite steps to continue with the labs.
