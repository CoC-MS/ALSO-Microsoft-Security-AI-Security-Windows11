# 🛡️ ALSO Microsoft Security AI Security - Windows 11

> Windows 11 security policy exports and supporting resources designed to reduce unauthorized third-party AI access while maintaining a productive user experience. The baseline describes controls for application installation and execution, Microsoft Edge, Microsoft Store and proxy bypass, non-Microsoft AI services, compliant-device access, and AI agent governance.

> [!NOTE]
> **Documentation preview:** The main `README.md` is unchanged. This page previews a refreshed public-facing landing page. See [Public documentation](docs/public/README.md) for the supporting guides.

> [!IMPORTANT]
> These exports are starting points, not ready-made tenant configurations. The source project specifies corporate-owned Windows 11 devices. Review licensing, settings, tenant-specific values, dependencies, and assignments before use. Import Conditional Access policies in **OFF** state and pilot reviewed changes before expanding deployment.

| Resource | Description |
| --- | --- |
| 📂 **[File structure](docs/public/file-structure.md)** | Find the policy exports and supporting resources in this repository. |
| 🔐 **[Conditional Access policy guide](docs/public/conditional-access-policies.md)** | Review the seven exported Conditional Access policies and their caveats. |
| 🚀 **[Prerequisites](docs/public/prerequisites.md)** | Check licensing, tenant setup, and dependencies before import. |
| 📖 **[Policy naming](docs/public/policy-naming.md)** | Understand the naming components used by device and Conditional Access policies. |
| 📥 **[How to import](docs/public/how-to-import.md)** | Import selected resources and validate the result. |
| 🐛 **[Reporting issues](docs/public/reporting-issues.md)** | Report problems in the intended Windows 11 project without disclosing tenant information. |
| 🛡️ **[Security information](SECURITY)** | Read the repository's security guidance. |
| 📜 **[License](LICENSE)** | Read the repository license. |

---

## 📦 Policy resources

The exports are organized under [`ALSO_AI_SECURITY_POLICIES`](ALSO_AI_SECURITY_POLICIES). Select policies and supporting resources for the target tenant; do not assume that every export should be imported or assigned.

| Resource | JSON files | Purpose |
| --- | ---: | --- |
| [SettingsCatalog](ALSO_AI_SECURITY_POLICIES/SettingsCatalog/) | 12 | Windows device configuration policies. |
| [CompliancePolicies](ALSO_AI_SECURITY_POLICIES/CompliancePolicies/) | 4 | Device compliance policy exports. |
| [ConditionalAccess](ALSO_AI_SECURITY_POLICIES/ConditionalAccess/) | 7 | Conditional Access policies, including internal-user and Agent 365 controls. |
| [Groups](ALSO_AI_SECURITY_POLICIES/Groups/) | 4 | Group exports referenced by Conditional Access policies. |
| [NamedLocations](ALSO_AI_SECURITY_POLICIES/NamedLocations/) | 1 | Named location export referenced by Conditional Access policies. |
| [MigrationTable.json](ALSO_AI_SECURITY_POLICIES/MigrationTable.json) | 1 | Supporting migration data. |

Counts describe the files currently in each category; they do not represent recommended assignments or a guarantee that every feature is licensed. Review each export and map referenced resources to the destination tenant.

## 🌐 Windows 11 coverage

The source project describes controls to restrict third-party AI access while supporting a productive Windows 11 environment. Areas called out in the project include:

- Application installation and execution controls, Microsoft Edge as the approved browser, and Microsoft Store restrictions.
- Proxy-bypass and non-Microsoft AI service controls, including separate Defender portal configuration.
- Windows compliance requirements and Conditional Access for corporate-managed devices.
- Agent 365 Conditional Access policies for agent identity risk, resource access, compliant devices, and compliant networks.

Some related controls are configured separately in Microsoft Intune, Defender, Defender for Cloud Apps, or Teams; importing the JSON files alone does not configure those services. See [Prerequisites](docs/public/prerequisites.md) and review the setup guidance in the existing root README before deployment.

> [!WARNING]
> CA204 and CA205 reference an example internal-users group; review its membership or replace it. CA501–CA505 require an Agent 365 licence and Agent 365 portal onboarding according to the source project. Verify all assignments, dependencies, and policy settings before enabling anything.

## 🚀 Getting started

1. Review [Prerequisites](docs/public/prerequisites.md) and the source README's [licensing information](README.md#works-with-following-licenses).
2. Inspect the [policy exports](docs/public/file-structure.md) and [Conditional Access guide](docs/public/conditional-access-policies.md); select only the resources needed for the tenant.
3. Follow [How to import](docs/public/how-to-import.md), keep Conditional Access policies OFF during import, and validate with a controlled pilot.
