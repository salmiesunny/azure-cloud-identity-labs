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


