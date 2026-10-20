# 🔐 Conditional Access policy guide

**Disclaimer:** Licensing prerequisites and feature availability listed on this page may be incorrect, incomplete, or outdated. We strongly recommend verifying all licensing information against the latest official Microsoft licensing documentation before making any purchasing or deployment decisions.

**Enterprise licenses:** [Microsoft Enterprise Plan Comparison](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/bade/documents/products-and-services/en-us/education/Modern-Work-Plan-Comparison-Enterprise.pdf)

**SMB licenses:** [Microsoft SMB Plan Comparison](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/bade/documents/products-and-services/en-us/education/Modern-Work-Plan-Comparison-Enterprise.pdf)

[Public documentation](README.md)

Review each JSON's complete conditions, assignments, exclusions, grant controls, and session controls before use; names alone do not describe the full configuration.

> [!IMPORTANT]
> Import Conditional Access policies in **OFF** state. Review target groups and dependencies, and test intended sign-in behavior before enabling policies.

| Package | Policies |
| --- | --- |
| BP | CA204 and CA205 |
| E7 | CA204, CA205, and CA501–CA505 |

## BP policies

### BP-ALSO-CA205-Internals-AllApps-Windows-Grant-RequireCompliantDevice

Requires Windows devices to be compliant before internal users can access cloud applications. Remember to set compliance requirements in Intune for Windows first. Check Windows repo to find compliance templates for Windows. PS: Verify the included group(s) and/or add your custom groups which have all internals in it. ALSO- All Internals is added as an example. This group needs to be imported to Entra, otherwise policy will fail on import with following message:

See the preserved error in [Dependencies and import errors](dependencies-and-import-errors.md).

---

### BP-ALSO-CA204-Internals-AllApps-AnyPlatform-Block-UnknownPlatforms

Blocks internal users from signing in using unsupported or unrecognized device platforms. PS: Verify the included group(s) and/or add your custom groups which have all internals in it. ALSO- All Internals is added as an example. This group needs to be imported to Entra, otherwise policy will fail on import with following message:

See the preserved error in [Dependencies and import errors](dependencies-and-import-errors.md).

## Agent 365 Conditional Access policies

## 🤖 Agent Policies

> [!IMPORTANT]
> **All Agent policies (CA501-CA505) require an Agent 365 license to be assigned and Agent 365 portal onboarding to be completed before import. Otherwise, the policies will fail during import and display the following error message.**

See the preserved error in [Dependencies and import errors](dependencies-and-import-errors.md).

### A365-ALSO-CA501-Agents-AllApps-AnyPlatform-Block-HighRiskAgent

Prevents agent identities from accessing tenant resources when Microsoft identifies the agent as having a high risk level

---

### A365-ALSO-CA502-Agents-AllAgentIdentities-AllAgentResources-Block-AllExceptSelected

Denies access for all agent identities by default. Only explicitly approved or excluded agents are permitted. Agent approval can also be managed through the Agent 365 portal

---

### A365-ALSO-CA503-Agents-AllAgentUsers-Grant-RequireCompliantDevice

Restricts agent user access to devices that meet organizational compliance requirements.

---

### A365-ALSO-CA504-Agents-AllAgentUsers-AllResources-Block-RiskyAgents

Blocks agent users when Microsoft Entra ID Protection classifies the identity as medium or high risk.

---

### A365-ALSO-CA505-Agents-AllAgentUsers-AllResources-Grant-RequireCompliantNetWork

Allows agent user access only from locations connected through the Global Secure Access compliant network.

The current E7 artifact is named `A365-ALSO-CA505-Agents-AllAgentUsers-AllResources-Block-RequireCompliantNetWork.json`, matching the current Conditional Access repository source. Review its JSON settings rather than relying on historical wording.
