# Privileged Account Leaver
## Lifecycle Workflow Custom Extension

This template demonstrates how to **automatically offboard privileged (admin) accounts** when a user leaves the organization or no longer requires elevated access.

The solution combines **Lifecycle Workflows**, **Custom Extensions**, and the **Inbound API Provisioning Service** to ensure privileged accounts are disabled securely, consistently, and audibly.

---

## Solution Overview

This implementation uses the following components:

- **Lifecycle Workflows**  
  Detects leaver and privilege‑removal events.

- **Custom Extension (Logic App)**  
  Executes external offboarding logic.

- **Inbound API Provisioning Service**  
  Disables and manages the privileged account lifecycle.

- **Managed Identity**  
  Provides secure, credential‑free authentication to Microsoft Graph.

---

## Why Use the Inbound API Provisioning Service?

Using the Inbound API Provisioning Service for privileged account offboarding provides:

1. **Immediate Secure Deactivation**  
   Admin accounts are disabled via a Microsoft‑managed, auditable service.

2. **Audit & Compliance Logging**  
   All actions are recorded and traceable for compliance requirements.

3. **Retention & Deletion Control**  
   Supports delayed deletion based on organizational policy.

4. **Centralized Offboarding Flow**  
   All privileged account actions are routed through a single service.

5. **Operational Safety**  
   Actions can be traced and reviewed, reducing risk during offboarding.

---

## Prerequisites

> **Note**  
> Follow the setup instructions in  
> 📄 **[Create Inbound Provisioning API](../Create%20Inbound%20Provisioning%20API.md)**  
> before continuing.

> **Important**  
> API provisioning only works for **eligible privileged accounts**.  
> If a privileged account is *active* (for example, credentials are checked out), higher‑privilege access is required and this approach cannot be used.

---

## Part 1: Create the Lifecycle Workflow Custom Extension

### Step 1: Navigate to Lifecycle Workflows

1. Open the **Entra Admin Center**  
   https://entra.microsoft.com
2. Go to **Identity Governance** → **Lifecycle Workflows**
3. Select **Custom Extensions**
4. Choose **Add custom extension**

---

### Step 2: Configure Basic Details

- **Name**: `Admin-Account-Leaver-Extension`  
- **Description**: `Offboards privileged admin accounts for leavers`

Select **Next**.

---

### Step 3: Configure the Endpoint

1. **Endpoint configuration**: `Create new Logic App`
2. **Subscription**: Select your Azure subscription
3. **Resource Group**: Select or create one
4. **Logic App name**: `lcw-admin-leaver-extension`
5. **Region**: Select your preferred region
6. Select **Create Logic App**

---

### Step 4: Review and Create

Verify:
- Custom extension name
- Logic App target
- Authentication (configured later)

Select **Create**.

---

## Part 2: Configure the Logic App

### Step 5: Verify Logic App Creation

1. Open the **Azure Portal**
2. Navigate to **Logic Apps**
3. Open `lcw-admin-leaver-extension`
4. Select **Logic App Designer**

You should see a preconfigured HTTP trigger:
- **Trigger**: When an HTTP request is received
- **Method**: POST
- **Schema**: Empty

---

### Step 6: Switch to Code View

1. Select **Code view**
2. Replace the existing JSON with the sample definition below

---

### Sample Logic App Definition

```json
{
  "...": "Full JSON unchanged for brevity in explanation"
}
``
