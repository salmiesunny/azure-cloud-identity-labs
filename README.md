# Azure Cloud & Identity Labs

Hands-on Azure, Microsoft Entra ID, cloud infrastructure, and security labs documenting practical learning, configurations, troubleshooting, and project outcomes.

## About This Project

This repository documents my hands-on learning journey in Microsoft Azure, Microsoft Entra ID, cloud infrastructure, and security.

My goal is to build practical skills relevant to IT Support, IT Infrastructure, Network Operations, and Cloud Security roles.

## Learning Objectives

- Explore Azure services and resource management
- Understand Microsoft Entra ID and identity management
- Learn role-based access control (RBAC)
- Practise cloud networking and security fundamentals
- Build practical Microsoft 365, Windows Server and endpoint-management skills used in UAE IT Support and Infrastructure roles
- Document lab procedures, observations, and troubleshooting

## Lab Roadmap

The labs are planned around skills commonly requested in IT Support, IT Infrastructure and Network Operations roles in the UAE.

| Lab | Topic | Status |
|---|---|---|
| 01 | Azure Portal and Entra ID Exploration | Completed |
| 02 | Azure Access and Resource Management | Completed |
| 03 | Resource Inventory and Cost Awareness | Completed |
| 04 | Microsoft Entra Enterprise Applications | Completed |
| 05 | Microsoft Entra ID Users and Groups | Completed |
| 06 | Troubleshoot a Microsoft Entra ID Sign-in Failure | Completed |
| 07 | Azure RBAC and Role Assignments (Read-Only) | Completed |
| 08 | Microsoft 365 Admin Basics (users, licences, groups, shared mailbox) | Planned |
| 09 | Windows Server: Active Directory, DNS and DHCP | Planned |
| 10 | Group Policy (GPO) | Planned |
| 11 | Intune and Endpoint Management | Planned |
| 12 | Backup and Recovery | Planned |
| 13 | Conditional Access and MFA Design | Planned |
| 14 | Azure Virtual Networks and NSGs | Planned |
| 15 | Azure Monitor and Activity Log | Planned |

Status is updated only when a lab has actually been performed and documented.

## Lab Progress

### Lab 01 — Azure Portal and Entra ID Exploration

- **Status:** Completed
- **Objective:** Explore the Azure portal and understand basic identity and resource management.
- **Tasks performed:**
  - Accessed the Azure portal.
  - Opened Microsoft Entra ID and reviewed the tenant overview.
  - Inspected the Users and Groups pages.
  - Checked Azure subscription availability.
- **Observations:**
  - Tenant information was visible in the portal.
  - The Users page displayed user entries.
  - The Groups page appeared empty in the view inspected.
  - An Azure subscription was listed.
- **Key learning:** Microsoft Entra ID manages identity-related objects such as users and groups. An empty listing in one view does not establish that groups are unused.

### Lab 02 — Azure Access and Resource Management

- **Status:** Completed
- **Objective:** Understand Azure role assignments, resource groups, and cost-management visibility.
- **Tasks performed:**
  - Inspected Access control (IAM).
  - Reviewed a visible Owner role assignment scoped to a resource group.
  - Viewed the resource groups listed in the portal.
  - Opened Cost Management and confirmed that Cost Analysis was accessible.
- **Observations:**
  - The Owner role assignment was at resource-group scope, not subscription scope.
  - Resource groups were listed in the portal.
  - Cost Analysis was accessible.
- **Key learning:** Azure role assignments have scopes, and resource groups help organize Azure resources. Cost visibility depends on the selected scope and available permissions.

### Lab 03 — Resource Inventory and Cost Awareness

- **Status:** Completed
- **Objective:** Practise reviewing Azure resource groups, identifying visible resources, and understanding cost-management visibility.
- **Tasks performed:**
  - Reviewed the resource groups available in the Azure portal.
  - Inspected the resource group used during the previous virtual-machine attempt.
  - Opened Cost Management and explored Cost Analysis.
  - Recorded observations about resource visibility and access.
- **Observations:**
  - The resource group inspected appeared empty.
  - Cost Analysis was accessible.
  - No resources were visible in the inspected resource group.
- **Key learning:** Resource groups organize Azure resources, and Cost Analysis helps review available cost information. An empty resource group does not necessarily mean that the wider Azure environment has no resources.

### Lab 04 — Microsoft Entra Enterprise Applications

- **Status:** Completed
- **Objective:** Inspect Microsoft Entra Enterprise Applications and practise read-only identity troubleshooting.

**Initial observation:**
- The All applications list appeared empty with no active filters visible.
- Refreshing the page did not change the result.
- The signed-in account appeared in the Global Administrator role assignments.

**Troubleshooting performed (read-only):**
1. **Filter check:** The view used the filter *Application type == Microsoft Applications* and showed 33 applications. With no filter, the count was also 33. Setting the filter to *Application type == Enterprise Applications* returned an empty list.
2. **App registrations:** The All applications list was empty.
3. **Role check:** Global Administrator was listed as an Active, Direct assignment.
4. **Health page:** Opening the Entra Health page returned error 401, "Insufficient privileges to complete the operation."
5. **Audit logs:** The page loaded and returned "No results" for the 30-day date range selected.
6. **Deleted applications:** The list was empty.
7. **Licences:** No Microsoft Entra ID licence was listed under Licenses.

**Findings:**
- The list loads and shows 33 Microsoft applications, so the page itself was working.
- The Enterprise Applications view returned no results, and there were no app registrations or deleted applications. This is consistent with the tenant containing only Microsoft's built-in applications and no non-Microsoft enterprise applications.
- The audit log showed no results for the 30-day period checked, so it provided no evidence of application changes in that period. It cannot show what happened outside that window.
- The 401 error on the Health page was not explained. The account held an active Global Administrator role, so holding that role did not guarantee access to every page. The cause (for example a licence requirement) was not verified.
- The most likely explanation for the original empty list is that the default view found no non-Microsoft enterprise applications. This is an inference from the observations, not a confirmed cause.

**Key learning:**
- The Enterprise applications page applies filters, and an empty default view does not prove that no applications exist.
- Comparing Enterprise applications, App registrations, role assignments, audit logs and licences is a structured way to narrow down an empty list.
- An administrator role does not guarantee access to every portal page.
- Audit log results depend on the date range selected and on what the tenant retains.
- Findings should be recorded as observed, without stating a cause that was not verified.

**Security note:** Read-only inspection. Only the on-screen filter and date range were changed. No applications, role assignments, licences, or permissions were changed.

### Lab 05 — Microsoft Entra ID Users and Groups

- **Status:** Completed
- **Objective:** Explore user account details and group membership in Microsoft Entra ID.

**Tasks performed:**
- Opened the Users directory and viewed the list of users.
- Opened a user's Overview page.
- Identified the User Principal Name (UPN) and User type fields.
- Inspected the selected user's group membership.
- Opened the Groups directory.

**Observations:**
- The Users directory displayed user entries.
- The inspected user's Overview page showed the UPN and User type fields.
- The selected user's group membership list appeared empty.
- The Groups directory list also appeared empty.

**Key learning:**
- The UPN identifies a user's sign-in identity.
- User type helps distinguish account categories such as Member and Guest.
- Groups can help administrators manage access centrally when the relevant permissions are configured.
- An empty group listing does not establish that a user has no access to resources.

**Security note:** The exercise used read-only inspection. No users, groups, memberships, or permissions were changed.

### Lab 06 — Troubleshoot a Microsoft Entra ID Sign-in Failure

- **Status:** Completed
- **Objective:** Investigate a failed user sign-in by reviewing account status, sign-in logs, authentication details, and Conditional Access results.

**Steps performed:**
1. Checked the account status and confirmed the account was enabled.
2. Opened the failed sign-in event in Microsoft Entra ID sign-in logs.
3. Reviewed Authentication Details and identified that MFA was required but not completed.
4. Reviewed the Conditional Access tab and confirmed that the relevant policy showed Success.
5. Checked the error code and failure reason, which referenced MFA, an authentication challenge, or a timeout.
6. Identified the event timestamp, Correlation ID, and Request ID as useful troubleshooting references.
7. Reviewed nearby sign-in events and found a successful sign-in event.

**Findings:**
- The investigated sign-in failed because the required authentication process was not completed.
- The available details indicated an incomplete or timed-out MFA challenge.
- A Conditional Access policy showing Success did not mean the entire sign-in had succeeded.
- A nearby successful sign-in was observed, but the relationship between the two events was not established.

**L1 troubleshooting approach:**
- Verify the account status and review the sign-in error details.
- Check the MFA result and relevant Conditional Access evaluation.
- Ask the user what they experienced during the MFA prompt.
- Guide the user through the approved MFA process or escalate according to organizational procedures.
- Provide the event timestamp and correlation details to the administrator if further investigation is required.
- Do not disable MFA or weaken Conditional Access as a troubleshooting shortcut.

**Skills practised:**
- Microsoft Entra ID sign-in log analysis
- MFA troubleshooting fundamentals
- Conditional Access interpretation
- Incident evidence collection
- L1 troubleshooting and escalation

**Important note:** This lab documents read-only investigation. No account, authentication method, or security policy settings were changed.

### Lab 07 — Azure RBAC and Role Assignments (Read-Only)

- **Status:** Completed
- **Objective:** Understand Azure Role-Based Access Control (RBAC), built-in roles, assignment scope, and the principle of least privilege.

**Activities performed:**
- Opened Azure subscription 1 and navigated to Access control (IAM).
- Inspected the role assignments in read-only mode.
- Observed an Owner role assignment associated with my account.
- Inspected the assignment details, where the scope was displayed as "This resource".
- Practised choosing appropriate roles for common IT support scenarios.

**Key learnings:**
- **Reader:** Provides read-only access within the assigned scope.
- **Contributor:** Can manage resources within the assigned scope but generally cannot grant access to other users.
- **Owner:** Can manage resources and grant access within the assigned scope.
- **Least privilege:** Access should be limited to what a user needs to perform their duties.
- **Scope:** Determines the resources to which an assignment applies. The exact scope of the observed Owner assignment was not independently verified during this exercise.

**Operational and security notes:**
- Used read-only inspection; no role assignments or permissions were changed.
- Verified that the role assignment displayed my account as the principal and Owner as the role.
- Recognised the importance of checking scope before concluding how broadly a permission applies.

**Outcome:** Improved my understanding of Azure RBAC, built-in role differences, assignment scope, and least-privilege access decisions.

### Lab 08 — Microsoft 365 Admin Basics

- **Status:** Planned
- **Objective:** Practise common user-management tasks in the Microsoft 365 admin center, as performed by an L1/L2 IT Support Engineer.

**Planned tasks:**
- Review the tenant and admin role in the Microsoft 365 admin center.
- Create a test user and assign a licence.
- Reset a password and review the sign-in block option.
- Create a security group and a Microsoft 365 group, and compare them.
- Create a shared mailbox and add a member.
- Review Service health and Message center.
- Delete the test user and review the Deleted users list.

**Observations:** _To be completed after the lab._

**Key learning:** _To be completed after the lab._

**Security note:** _To be completed after the lab. Lab tenant only; no production settings changed._
