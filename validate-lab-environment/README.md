# Validate lab environment

## **Lab Environment Setup**
Before starting the labs, ensure your environment is ready. This page will guide you through the setup process, ensuring all prerequisites are met. Use **Microsoft Edge** or any supported browser.

### **Prerequisites**
- Azure subscription → [Create Free Subscription](https://azure.microsoft.com/free)  
- Azure DevOps organization → [Create Organization](https://aex.dev.azure.com)  
- Install tools:  
  - [Git for Windows](https://gitforwindows.org/)
  - [Visual Studio Code](https://code.visualstudio.com/)
  - [Azure CLI](https://learn.microsoft.com/cli/azure/install-azure-cli) (on self-hosted agent machine)
  - [.NET 8 SDK](https://dotnet.microsoft.com/download/visual-studio-sdks) (on self-hosted agent machines)

---

## **Create Azure DevOps Organization**

1. If you don’t have a Microsoft Account + Azure subscription:  
   - Create an MSA → [account.microsoft.com](https://account.microsoft.com)  
   - Sign up for Azure Free → [azure.microsoft.com/free](https://azure.microsoft.com/free)  

2. In [Azure Portal](https://portal.azure.com), search **Azure DevOps** → click **Azure DevOps organizations**.  

3. Go to [aex.dev.azure.com](https://aex.dev.azure.com) → click **Create new organization**.  

4. Accept Terms → keep default org name (must be unique) → choose nearest region.  

5. In **Organization Settings**:  
   - **Billing** → link to Azure subscription → set **Paid parallel jobs (MS Hosted)** = 1.  
   - **Pipelines > Settings** → disable classic build & release pipelines.  
   - **Security > Policies** → enable **Allow public projects**.  

---

## **Create and Configure Azure DevOps Project**

### **1. Create Project**
- Navigate to your DevOps org → click **New Project**.  
- Settings:  
  - **Name**: eShopOnWeb  
  - **Visibility**: Private  
  - **Version Control**: Git  
  - **Work Item Process**: Scrum  

### **2. Import Repository**
- Open **Repos > Files → Import Repository**.  
- URL: `https://github.com/MicrosoftLearning/eShopOnWeb`  
- Set **main** branch as default.  

Repository structure highlights:
- `.ado` → older contains Azure DevOps YAML pipelines.
- `.devcontainer` → folder container setup to develop using containers (either locally in VS Code or GitHub Codespaces).
- `.azure` → folder contains Bicep & ARM infrastructure as code templates.
- `.github` → container YAML GitHub workflow definitions.
- `src` → contains the .NET 8 website used on the lab scenarios.

### **3. Create Service Connection**
- In **Project Settings > Pipelines > Service connections → Create**.  
- Select **Azure Resource Manager → App registration (automatic)**.  
- Scope: **Workload Identity federation + Subscription**.  
- Fill in:  
  - **Subscription** → your Azure sub  
  - **Resource Group** → choose/create  
  - **Name** → `azure subs`  
- Save (leave “Grant access permission to all pipelines” unchecked).  

✅ Done — you can now continue with the labs.