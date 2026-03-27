# Inbound API Provisioning - Application

This template demonstrates how to automatically provision privileged admin accounts when users join the organization using Lifecycle Workflows custom extensions and the Inbound API Provisioning service.

---

## Part 1: Inbound API Provisioning Service for Admin Accounts

### What is the Inbound API Provisioning Service?

The **Inbound API Provisioning Service** is a Microsoft Entra ID capability that allows you to programmatically provision users into your tenant through a standardized API. Instead of creating users directly via Microsoft Graph API, this service provides:

- **Bulk provisioning capabilities** with better performance
- **Attribute mapping and transformation** through provisioning configuration
- **Built-in deduplication and matching logic**
- **Audit logging and monitoring** through the provisioning logs
- **Schema validation** to ensure data consistency

### Why Use It for Admin Accounts?

Using the Inbound API Provisioning Service for privileged accounts offers several advantages:

1. **Centralized Management**: All admin account provisioning flows through a single, auditable service
2. **Attribute Mapping**: Define once how attributes should be mapped from source data to Entra ID
3. **Separation of Concerns**: Provisioning logic is separate from your custom extension logic
4. **Compliance**: Built-in logging meets audit requirements for privileged account creation
5. **Idempotency**: The service handles duplicate requests gracefully

### Setting Up the Inbound API Provisioning Application

#### Step 1: Create the API-Driven Provisioning Application

1. Navigate to **Entra ID Admin Center** → **Enterprise Applications** → **+ New Application**
2. Search for **API-driven provisioning to Microsoft Entra ID**
3. Name it: `Admin Account Provisioning API`
4. Click **Create**

#### Step 2: Enable API-Driven Provisioning

1. In the newly created enterprise application, go to **Provisioning**
2. Click **Get started**
3. Set **Provisioning Mode** to **Automatic**
4. Under **Settings**, select **Send an email notification when a failure occurs** and type in an email address.
5. Click **Test Connection** and **Save**

#### Step 3: Configure Attribute Mappings

1. In the **Provisioning** section, click **Edit attribute mappings**
2. Under **Mappings**, select **Provision Azure Active Directory Users**
3. Configure the following attribute mappings:

| Source Attribute | Target Attribute | Matching type |
|-----------------|------------------|-------------------|
| `userName` | `userPrincipalName` | Direct |


4. Click **Save** to apply the mappings
