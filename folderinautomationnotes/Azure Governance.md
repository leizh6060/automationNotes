https://learn.microsoft.com/en-us/azure/azure-monitor/fundamentals/overview
https://learn.microsoft.com/en-us/training/paths/security-governance-compliance/
# Enforce governance with Azure Policy and resource locks
## Policy scope hierarchy—where to assign matters

Policy assignments inherit through the Azure resource hierarchy: management group → subscription → resource group → resource. The scope you choose determines which resources the policy evaluates.

Key built-in definitions for a security baseline include:

- **"Transparent data encryption on SQL databases should be enabled"** - Audit or Deny effect; targets `Microsoft.Sql/servers/databases` resources. Detects SQL databases without TDE encryption.
- **"Secure transfer to storage accounts should be enabled"** - Audit or Deny effect; targets `Microsoft.Storage/storageAccounts` resources. Blocks storage accounts that allow HTTP traffic.
- **"Storage accounts should restrict network access"** - Audit effect; evaluates storage account network rules to ensure public access is limited.
- **"Azure Key Vault should use private link"** - Audit effect; detects Key Vaults exposed to the public internet.
- **"Diagnostic logs in Azure Key Vault should be enabled"** - AuditIfNotExists effect; checks whether Key Vault diagnostic settings are configured.
# Configure Defender for Cloud and manage security standards
## Environment settings—configure before you govern
Defender for Cloud can automatically deploy:

- **Azure Monitor Agent**—replaces the retired Log Analytics agent (MMA) and collects security events from VMs and Arc-connected machines
- **Defender for Endpoint sensor**—provides endpoint detection and response capabilities on Windows and Linux VMs
- **Vulnerability assessment agent**—scans VMs for missing patches, misconfigurations, and installed software vulnerabilities
# Deploy remediation controls at scale

# Evaluate regulatory compliance in Defender for Cloud


Core Governance Services // from google

| Service                       | Primary Purpose                                     | Key Use Case                                                                 |     |
| ----------------------------- | --------------------------------------------------- | ---------------------------------------------------------------------------- | --- |
| **Azure Management Groups**   | Hierarchical alignment of subscriptions.            | Applying global policies or access rights across multiple subscriptions.     |     |
| **Azure Policy**              | Real-time evaluation and enforcement of standards.  | Restricting resource deployment to allowed regions or blocking public IPs.   |     |
| **Microsoft Purview**         | Data governance, risk, and compliance management.   | Discovering, classifying, and tracking the lineage of sensitive data assets. |     |
| **Resource Graph**            | High-performance resource exploration and querying. | Auditing resource compliance status at scale across multiple tenants.        |     |
| **Microsoft Cost Management** | Financial governance and spending visibility.       | Setting up organizational budgets and unexpected-spend alerts.               |     |
| **Resource Locks**            | Prevent accidental deletion or modifications.       | Protecting mission-critical express routes or production databases.          |     |
