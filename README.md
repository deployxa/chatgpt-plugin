# Deployxa for ChatGPT (`deployxa_chatgpt`)

Deploy applications, stream live build logs, diagnose failure root causes, and search & register custom domains directly inside ChatGPT.

---

## Setup Guide for ChatGPT Custom GPT

### Step 1: Create a Custom GPT
1. In ChatGPT, navigate to **Explore GPTs** $\rightarrow$ **+ Create**.
2. Go to the **Configure** tab.
3. Set the Name to `Deployxa Cloud` and upload an icon (from `https://deployxa.com/icon.png`).
4. Set the Description: `Deploy web apps, diagnose build failures, stream logs, and register custom domains autonomously.`

### Step 2: Paste System Instructions
Copy the instructions from [`instructions.md`](./instructions.md) into the **Instructions** text box.

### Step 3: Add the Action
1. Under **Actions**, click **Create new action**.
2. Under **Schema**, select **Import from URL** and enter:
   `https://raw.githubusercontent.com/deployxa/chatgpt-plugin/main/openapi.json`
   *(or paste the contents of [`openapi.json`](./openapi.json))*.
3. Under **Authentication**, select:
   - **OAuth**:
     - Client ID / Client Secret: (From Deployxa Dashboard)
     - Authorization URL: `https://mcp.deployxa.com/oauth/authorize`
     - Token URL: `https://mcp.deployxa.com/oauth/token`
     - Scope: `projects:read projects:write deployments:read deployments:write domains:read domains:write logs:read`
   - Or **API Key**:
     - Auth Type: `Bearer`
     - Token: `dxa_...` (from https://deployxa.com/dashboard/api-keys)

### Step 4: Publish
Click **Save** / **Publish** (to *Anyone with a link* or *Public* on the GPT Store).
