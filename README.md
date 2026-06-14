# office365-sharepoint-governance

```markdown
# Enterprise Office 365 & SharePoint Identity Governance Framework

This repository serves as a professional documentation blueprint outlining the identity access management (IAM), data lifecycle governance, and multi-tenant security architecture implemented to protect enterprise resources inside **Microsoft 365, Azure Active Directory (Entra ID), and SharePoint Online**.

---

## 🏢 Governance & Security Framework Core
* **Identity Protection:** Conditional Access Policies and Multi-Factor Authentication (MFA) enforcement.
* **Role-Based Access Control (RBAC):** Implementing Least-Privilege Access across M365 Security Groups.
* **SharePoint Document Lifecycles:** Designing secure document libraries with strict external sharing restrictions and data loss prevention (DLP) parameters.

---

## 🛠️ Access & Compliance Configuration Blueprint

### 1. Tenant Security & Conditional Access Matrix
To protect corporate accounts from credential theft, the following **Microsoft Entra ID (Azure AD)** security controls are enforced:
* **MFA Registration Enforcement:** Mandatory Microsoft Authenticator onboarding for all internal corporate users.
* **Location-Based Access Controls:** Blocking authentication requests originating outside vetted geographic perimeters (e.g., restricted countries/regions).
* **Device Compliance Gates:** Ensuring only company-registered, healthy endpoints can sync internal corporate data.

### 2. Role-Based Access Control (RBAC) & Dynamic Security Groups
Instead of manually provisioning user accounts, identity lifecycle management is structured around **Active Directory Security Groups**:

| Security Group Name | Entra ID / M365 Role | Access Level Scope |
| :--- | :--- | :--- |
| `M365-Global-Admins` | Global Administrator | Full Tenant Configuration Control (Restricted to < 3 accounts) |
| `M365-IT-Support-L2` | Helpdesk Administrator | Password Resets, Endpoint Management, Basic Triage |
| `O365-Finance-Staff` | Restricted Exchange/SharePoint | Access to locked Finance Document Libraries only |

### 3. Enterprise SharePoint Online Governance
Document libraries are hardened against data leaks using strict external collaboration constraints:

* **External Sharing Boundaries:** Disabled "Anyone" (anonymous) sharing links globally. Sharing is limited to authenticated guests with organizational whitelist approvals.
* **Data Loss Prevention (DLP) Triggers:** Configured tenant-wide DLP policies inside Microsoft Purview to automatically flag, mask, or block documents containing sensitive data (e.g., credit card information, internal financial audits, passport numbers) from being shared externally.
* **Information Barriers:** Segmented distinct business departments to prevent unauthorized cross-collaboration and inadvertent access to confidential project files.

---
💡 *Maintained by Kyaw Thu Nay Aung — Microsoft 365 & Enterprise Systems Cloud Administrator.*

