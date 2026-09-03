[Understand Microsoft Entra ID](https://learn.microsoft.com/en-gb/training/modules/understand-azure-active-directory/)
With Microsoft Entra ID, you also have access to a set of features that aren’t natively available in AD DS, such as support for multi-factor authentication, identity protection, and self-service password reset.
you can use Microsoft Entra ID to provide more secure access to cloud-based resources for organizations and individuals by:

- Configuring access to applications
- Configuring single sign-on (SSO) to cloud-based SaaS applications
- Managing users and groups
- Provisioning users
- Enabling federation between organizations
- Providing an identity management solution
- Identifying irregular sign-in activity
- Configuring multi-factor authentication
- Extending existing on-premises Active Directory implementations to Microsoft Entra ID
- Configuring Application Proxy for cloud and local applications
- Configuring Conditional Access for users and devices
### Microsoft Entra tenants

Unlike AD DS, Microsoft Entra ID is multi-tenant by design and is implemented specifically to ensure isolation between its individual directory instances
Within an Azure subscription, you can create multiple Microsoft Entra tenants.
 A single Microsoft Entra tenant can support multiple Azure subscriptions.
### Microsoft Entra schema

The Microsoft Entra schema contains fewer object types than that of AD DS. Most notably, it doesn't include a definition of the computer class, although it does include the device class.
, because OUs in AD DS are used primarily for Group Policy scoping and delegation. You can accomplish equivalent arrangements by organizing objects based on their group membership.
### Characteristics of AD DS

AD DS is the traditional deployment of Windows Server-based Active Directory on a physical or virtual server.
# Examine Microsoft Entra ID as a directory service for cloud apps


When you deploy cloud services such as Microsoft 365 or Intune, you also need to have directory services in the cloud to provide authentication and authorization for these services.
# Compare Microsoft Entra ID P1 and P2 plans
The following features are available with the Microsoft Entra ID P1 edition:

- **Self-service group management**. It simplifies the administration of groups where users are given the rights to create and manage the groups. End users can create requests to join other groups, and group owners can approve requests and maintain their groups’ memberships.
- **Advanced security reports and alerts**. You can monitor and protect access to your cloud applications by viewing detailed logs that show advanced anomalies and inconsistent access pattern reports. Advanced reports are machine learning based and can help you gain new insights to improve access security and respond to potential threats.
- **Multi-factor authentication**. Full multi-factor authentication (MFA) works with on-premises applications (using virtual private network [VPN], RADIUS, and others), Azure, Microsoft 365, Dynamics 365, and third-party Microsoft Entra gallery applications. It doesn't work with non-browser off-the-shelf apps, such as Microsoft Outlook. Full multi-factor authentication is covered in more detail in the following units in this lesson.
- **Microsoft Identity Manager (MIM) licensing**. MIM integrates with Microsoft Entra ID P1 or P2 to provide hybrid identity solutions. MIM can bridge multiple on-premises authentication stores such as AD DS, LDAP, Oracle, and other applications with Microsoft Entra ID. This provides consistent experiences to on-premises line-of-business (LOB) applications and SaaS solutions.
- **Enterprise SLA of 99.9%**. You're guaranteed at least 99.9% availability of the Microsoft Entra ID P1 or P2 service. The same SLA applies to Microsoft Entra Basic.
- **Password reset with writeback**. Self-service password reset follows the Active Directory on-premises password policy.
- **Cloud App Discovery feature of Microsoft Entra ID**. This feature discovers the most frequently used cloud-based applications.
- **Conditional Access based on device, group, or location**. This lets you configure conditional access for critical resources, based on several criteria.
- **Microsoft Entra Connect Health**. You can use this tool to gain operational insight into Microsoft Entra ID. It works with alerts, performance counters, usage patterns, and configuration settings, and presents the collected information in the Microsoft Entra Connect Health portal.
- 
- In addition to these features, the Microsoft Entra ID P2 license provides extra functionalities:

- **Microsoft Entra ID Protection**. This feature provides enhanced functionalities for monitoring and protecting user accounts. You can define user risk policies and sign-in policies. In addition, you can review users’ behavior and flag users for risk.
- **Microsoft Entra Privileged Identity Management**. This functionality lets you configure additional security levels for privileged users such as administrators. With Privileged Identity Management, you define permanent and temporary administrators. You also define a policy workflow that activates whenever someone wants to use administrative privileges to perform some task.

# Examine Microsoft Entra Domain Services
//lei thought ad application authentication moodle
ecause Microsoft Entra ID can integrate with your local AD DS, when you implement Microsoft Entra Connect, users can utilize organizational credentials in both on-premises AD DS and in Microsoft Entra Domain Services.
If you choose to implement Microsoft Entra Domain Services, you need to be aware of the service's current limitations. These include:

- Only the base computer Active Directory object is supported.
- It’s not possible to extend the schema for the Microsoft Entra Domain Services domain.
- The organizational unit (OU) structure is flat and nested OUs aren't currently supported.
- There’s a built-in Group Policy Object (GPO), and it exists for computer and user accounts.
- It’s not possible to target OUs with built-in GPOs. Additionally, you can't use Windows Management Instrumentation filters or security-group filtering.
- 

[Create, configure, and manage identities](https://learn.microsoft.com/en-gb/training/modules/create-configure-manage-identities/)

Microsoft Entra ID allows you to define two different types of groups.

- **Security groups** - the most common type of groups and are used to manage access to shared resources. Members of a security group can include users, devices, and service principals. For example, you can create a security group for a specific security policy. By doing it this way, you can give a set of permissions to all the members at once, instead of having to add permissions to each member individually. This option requires a Microsoft Entra administrator.
- **Microsoft 365 groups** - provide collaboration opportunities by giving members access to a shared mailbox, calendar, files, SharePoint site, and more. This option also lets you give people outside of your organization access to the group. This option is available to users and admins.
- The second characteristic of a group that you need to be aware of is the **Membership Type**. This specifies how individual members are added to the group. The three types are:

- **Assigned** - members are added and maintained manually.
- **Dynamic User** - users are added and removed automatically based on rules that evaluate user attributes such as department, job title, or location.
- **Dynamic Device** - devices are added and removed automatically based on rules that evaluate device attributes. Applies to security groups only; Microsoft 365 groups support dynamic users but not dynamic devices.
 # Configure and manage device registration
- 
## Microsoft Entra joined devices

Microsoft Entra joined is intended for organizations that want to be cloud-first or cloud-only
### Scenarios for joined devices

Although Microsoft Entra joined is primarily intended for organizations that don't have an on-premises Windows Server Active Directory infrastructure, you can certainly use it in scenarios where:

- You want to transition to cloud-based infrastructure using Microsoft Entra ID and MDM like Intune.
- You can’t use an on-premises domain join, for example, if you need to get mobile devices such as tablets and phones under control.
- Your users primarily need to access Microsoft 365 or other SaaS apps integrated with Microsoft Entra ID.
- You want to manage a group of users in Microsoft Entra ID instead of in Active Directory. This scenario can apply, for example, to seasonal workers, contractors, or students.
- You want to provide joining capabilities to workers in remote branch offices with limited on-premises infrastructure.
Custom security attributes in Microsoft Entra ID are business-specific attributes (key-value pairs) that you can define and assign to Microsoft Entra objects. These attributes can be used to store information, categorize objects, or enforce fine-grained access control over specific Azure resources.

# Explore automatic user creation
![[Pasted image 20260828144917.png]]
### Components of SCIM (System for Cross-Domain Identity Management)

- **HCM system** - Applications and technologies that enable Human Capital Management process and practices that support and automate HR processes throughout the employee lifecycle.
- **Microsoft Entra Provisioning Service** - Uses the SCIM 2.0 protocol for automatic provisioning. The service connects to the SCIM endpoint for the application, and uses the SCIM user object schema and REST APIs to automate provisioning and deprovisioning of users and groups.
- **Microsoft Entra ID** - User repository used to manage the lifecycle of identities and their entitlements.
- **Target system** - Application or system that has SCIM endpoint and works with the Microsoft Entra provisioning to enable automatic provisioning of users and groups.


[Describe the core architectural components of Azure](https://learn.microsoft.com/en-gb/training/modules/describe-core-architectural-components-of-azure/)

![[Pasted image 20260828145257.png]]


[Azure Policy initiatives](https://learn.microsoft.com/en-us/training/modules/sovereignty-policy-initiatives/)
Azure Policy initiatives are a collection of Azure Policy definitions that are grouped together toward a specific goal or purpose.
# Cloud Adoption Framework for Azure
## Steps for cloud governance

Cloud governance is a continuous process. It requires ongoing monitoring, evaluation, and adjustments to adapt to evolving technologies, risks, and compliance requirements. The Cloud Adoption Framework - Govern methodology divides cloud governance into five steps.

[![Screenshot of a continuous process of Cloud governance.](https://learn.microsoft.com/en-us/training/modules/sovereignty-policy-initiatives/media/steps-for-cloud-governance.svg)]

he five core disciplines of cloud governance are as follows:

- **Cost management** – Evaluates and monitors costs, including controlling IT expenditures to establish well-defined cost management. It also includes adjusting resources according to demand. It's crucial to exercise control over cloud expenditure to derive greater value from your investments.
- **Security baseline** – Ensures compliance with IT security requirements by applying a security baseline to all adoption efforts.
- **Resource consistency** – Ensures consistency in resource configuration and enforcing practices for onboarding, recovery, and discoverability.
- **Identity baseline** – Ensures that the baseline for identity and access is enforced by consistently applying role definitions and assignments.
- **Deployment acceleration** – Accelerates the deployment of policies through centralization, consistency, and standardization across deployment templates.
- ## Cloud governance with Azure Policy

Azure's primary governance tool is [Azure Policy](https://learn.microsoft.com/en-us/azure/governance/policy/overview). Azure Policy facilitates the governance of all resources, including current and forthcoming resources. It helps to enforce organizational standards and to assess compliance at scale by establishing guardrails across various resources.
Some useful governance actions that you can enforce with Azure Policy include:

- Ensure that your team deploys Azure resources only to allowed regions.
- Enforce geo-replication rules to comply with your data residency requirements.
- Allow only certain virtual machine sizes for your cloud environment.
- Enforce the consistent application of taxonomic tags across resources.
- Recommend system updates on your servers.
- Allow multifactor authentication for all subscription accounts.
- Require resources to send diagnostic logs to an Azure Monitor Logs workspace.
- Azure Policy comes with built-in policy and initiative definitions for Storage, Networking, Compute, Security Center, and Monitoring. For example, if you define a policy that only allows a certain size for the virtual machines (VMs) to be used in your environment, that policy is invoked when you create a new VM and whenever you resize existing VMs. Azure Policy also evaluates and monitors all current VMs in your environment, including VMs that were created before the policy was created.
- ## Introduction to Azure Resource Manager
- ### Control plane

Azure Policy operates in the control plane to enforce rules and compliance on your resources. Azure Resource Manager manages all control plane operations in Azure and includes the different components that are centralized between the different services. Azure Policy is integrated with Azure Resource Manager.
![[Pasted image 20260828151045.png]]
### Data plane

The data plane is where the actual data operations occur, and Azure Policy ensures that the resources you interact with in the data plane are compliant with your policies. Data plane operations involve direct interaction with the data stored in a resource. Continuing with the previous example, you engage with the storage account to upload or download files. This interaction is handled directly by the data plane of the storage account rather than being managed by Azure Resource Manager.
Data plane operations aren't limited to REST API. Requests are made directly to the data endpoints of services (for example, accessing data in Microsoft Azure Storage, querying an SQL database, or reading secrets from Microsoft Azure Key Vault). Each Azure service handles these requests internally, bypassing Azure Resource Manager, and directly managing the data through its resource provider. Service-specific access controls, such as RBAC or access control lists (ACLs), often manage data plane permissions. The service responds with the data or result of the data operation, ensuring that the requester has the correct permissions.

//from Claude
**Control plane** manages Azure resources themselves — creating, configuring, updating, deleting, and organizing them. **Data plane** is where you actually interact with the content/data inside those resources.

**Control plane**

- Operations like: create a storage account, resize a VM, set up RBAC, configure networking, tag a resource
- Goes through **Azure Resource Manager (ARM)** — `management.azure.com`
- Governed by Azure RBAC roles (Owner, Contributor, Reader) and Azure Policy
- Example: creating a Key Vault, setting its access policies, deleting it

**Data plane**

- Operations like: reading/writing a blob, querying a database, getting a secret from Key Vault, sending a message to a Service Bus queue
- Goes through the resource's own endpoint (e.g. `https://myaccount.blob.core.windows.net`)
- Auth/authorization is often separate from ARM roles — many services (Key Vault, Storage, Cosmos DB) have their own data-plane RBAC roles or access policies distinct from the control-plane roles

**Why the distinction matters**

A classic gotcha: being "Owner" or "Contributor" on a Key Vault (control plane) doesn't automatically let you read secrets (data plane) if the vault uses Azure RBAC for data actions or a legacy access policy that doesn't include you. People expect resource-level permissions to cascade into the data itself, and it often doesn't — you need explicit data-plane role assignments (e.g., "Key Vault Secrets User") separate from "Contributor."

## Operation flows of Azure Resource Manager

Azure Resource Manager includes two scenarios for handling Azure requests: **Greenfield** and **Brownfield**.
. Six policy resources are available in Azure, and multiple different concepts apply to these Azure policy resources.
![[Pasted image 20260828152350.png]]
## Definitions

Azure Policy definitions describe resource compliance conditions and the effect to take if a condition is met. Several settings determine which resources are evaluated by any Azure Policy. You explore these settings in the next unit, **Azure Policy definitions**. The primary concept to which these settings can be applied is scope.

Scope in Azure Policy is the same as the levels of hierarchy for governance in Azure. Four levels of management scope are under the root tenant: the management groups, subscriptions, resource groups, and resources.
## Initiatives

Azure Policy initiatives, also known as a policy set, allow you to group several policy definitions to simplify assignments and management because you work with the initiatives as a single item. Initiatives offer a streamlined and automated approach to governance, allowing organizations to manage and monitor compliance at scale. The initiative definition contains all policy definitions to help track your compliance state for a larger goal, such as organizational compliance goals or compliance with regulatory frameworks.
## Assignments

Policy assignments define which resources are evaluated by a policy definition or initiative. Policy assignments can be done in the portal, an API call, or through the command line interface.

Policy and initiative definitions are deployed to a definition location (management group or subscription). This location determines the scope to which the initiative or policy can be assigned.


[Secure your Azure resources with Azure role-based access control (Azure RBAC)](https://learn.microsoft.com/en-gb/training/modules/secure-azure-resources-with-rbac/)

[Allow users to reset their password with Microsoft Entra self-service password reset](https://learn.microsoft.com/en-gb/training/modules/allow-users-reset-their-password/)

## xemptions

Use the Policy exemptions feature to _exempt_ a resource hierarchy or an individual resource from evaluation of initiatives or definitions. Resources that are _exempt_ count toward overall compliance but can't be evaluated or have a temporary waiver.
## Attestations

Policy attestations are used by Azure Policy to set compliance states of resources or scopes targeted by [manual policies](https://learn.microsoft.com/en-us/azure/governance/policy/concepts/effect-manual).
## Remediations

The policy remediation task feature is used to bring resources into compliance based on a definition and assignment. Resources that are noncompliant to a _modify_ or _deployIfNotExists_ definition assignment can be brought into compliance by using a remediation task. Resources that are newly created or updated that are applicable to a _deployIfNotExists_ or _modify_ definition assignment are automatically remediated.

# Azure Policy definitions
# Evaluation of resources through Azure Policy
## Evaluation triggers
## Evaluation timing
## Resource compliance states
## Enforcement Mode
_enforcementMode_ is a property of a policy assignment that lets you deactivate the enforcement of certain policy effects. This mode allows you to test the policy's outcome on existing resources without initiating the policy effect or triggering entries in the [Azure Activity log](https://learn.microsoft.com/en-us/azure/azure-monitor/essentials/platform-logs-overview). The _enforcementMode_ can be changed to Enabled after the policy is thoroughly tested.




## Policy enforcement and safe deployment best practices
Treating policy as code (keeping your policy definitions in source control, and whenever a change is made, testing and validating that change) allows you to automate testing and make sure that no manual error factor happens. The best practices framework focuses on minimizing the impact of policy changes while ensuring compliance, and it includes two aspects:

- **First aspect** - Start from Assignments of new policies with _enforcementMode_ Disabled. When assigning policies that include deny or modify actions, beginning with _enforcementMode_ Disabled allows you to view the compliance state and evaluate policy outcomes without triggering actions or denying operations. This "what-if" scenario minimizes impact and helps identify issues in the new policies or changes without disrupting the environment.
    
- **Second aspect** - Deploy policies in deployment rings. To control potential negative impacts, policies should be deployed gradually in smaller subsets and then in bigger sets. You can start with test and development environments and then move to production by applying the policy to a small subset first. This strategy helps in testing the policy thoroughly. Gradually expanding the scope (through deployment rings) can cover the full production environment.
- ![[Pasted image 20260830093344.png]]
## Reacting to policy state changes
![[Pasted image 20260830093458.png]]

# Secure your Azure resources with Azure role-based access control (Azure RBAC)
## What's Azure RBAC?

Azure RBAC is an authorization system built on Azure Resource Manager that provides fine-grained access management for resources in Azure.
# Allow users to reset their password with Microsoft Entra self-service password reset
