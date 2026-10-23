# azure-cloud-identity-labs
Hands-on Azure, Microsoft Entra ID, cloud infrastructure, and security labs documenting practical learning, configurations, troubleshooting, and project outcomes.


# Azure Cloud & Identity Labs

## About This Project

This repository documents my hands-on learning journey in Microsoft Azure, Microsoft Entra ID, cloud infrastructure, and security.

My goal is to build practical skills relevant to IT Support, IT Infrastructure, Network Operations, and Cloud Security roles.

## Learning Objectives

- Explore Azure services and resource management
- Understand Microsoft Entra ID and identity management
- Learn role-based access control (RBAC)
- Practise cloud networking and security fundamentals
- Document lab procedures, observations, and troubleshooting

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

- **Status:** In Progress
- **Objective:** Inspect Microsoft Entra Enterprise Applications and practise read-only identity troubleshooting.

**Tasks performed:**
- Opened Microsoft Entra ID → Enterprise applications.
- Selected the All applications view.
- Checked for visible active filters.
- Refreshed the page to check whether the results would load.

**Observations:**
- The application list appeared empty.
- No active filters were visible.
- Refreshing the page did not change the result.
- The signed-in account appeared in the Global Administrator role assignments.

**Conclusion:** The reason for the empty application list has not been established. The observation alone does not prove that the tenant has no applications or that a permissions issue exists. Further investigation would be needed.

**Security note:** No application settings, role assignments, or permissions were changed during these checks.

**Next step:** Practise user and group management concepts in a safe lab environment and continue learning how Microsoft Entra ID supports identity and access management.
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

**Status:** Completed

**Objective:** Investigate a failed user sign-in by reviewing account status, sign-in logs, authentication details, and Conditional Access results.

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

## Lab 07: Azure RBAC and Role Assignments (Read-Only)

### Objective
Understand Azure Role-Based Access Control (RBAC), built-in roles, assignment scope, and the principle of least privilege.

### Activities Performed
- Opened Azure subscription 1 and navigated to Access control (IAM).
- Inspected the role assignments in read-only mode.
- Observed an Owner role assignment associated with my account.
- Inspected the assignment details, where the scope was displayed as "This resource".
- Practised choosing appropriate roles for common IT support scenarios.

### Key Learnings
- **Reader:** Provides read-only access within the assigned scope.
- **Contributor:** Can manage resources within the assigned scope but generally cannot grant access to other users.
- **Owner:** Can manage resources and grant access within the assigned scope.
- **Least privilege:** Access should be limited to what a user needs to perform their duties.
- **Scope:** Determines the resources to which an assignment applies. The exact scope of the observed Owner assignment was not independently verified during this exercise.

### Operational and Security Notes
- Used read-only inspection; no role assignments or permissions were changed.
- Verified that the role assignment displayed my account as the principal and Owner as the role.
- Recognised the importance of checking scope before concluding how broadly a permission applies.

### Outcome
Improved my understanding of Azure RBAC, built-in role differences, assignment scope, and least-privilege access decisions.


