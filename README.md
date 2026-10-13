# 🛡️ ALSO Microsoft Security AI Security Windows 11 Policy Templates

>This baseline delivers a hardened Windows 11 configuration that minimizes the risk of unauthorized third-party AI access while maintaining a productive user experience. It restricts application installation and execution, enforces Microsoft Edge as the approved browser, blocks Microsoft Store and proxy bypass methods, limits access to non-Microsoft AI services, and requires compliant corporate-managed devices through Conditional Access policies. The baseline also includes Agent 365 Conditional Access controls for AI agent governance. Although designed as a high-security configuration, all settings can be customized to meet organizational requirements.

**Works with Microsoft 365 Business Premium + Defender Suite + Agent 365 (for Agent 365 policies) and up.**

> [!IMPORTANT]
> **⚠️ IMPORTANT: This solution works only on Intune enrolled corporate owned Windows 11 devices.**
---

> [!IMPORTANT]
> **⚠️ IMPORTANT: Read this before importing and using any policies.**

## Windows 11 AI Security Licensing Guide

Choose one standalone package. The available packages are cumulative: E7 contains every BP artifact plus the five Agent 365 Conditional Access policies.

### ✅ ALSO_AI_SECURITY_WINDOWS11_E7 — Full experience

Package: [`ALSO_AI_SECURITY_WINDOWS11_E7`](ALSO_AI_SECURITY_WINDOWS11_E7)

Use: when the tenant is licensed for all policies, including Agent 365.

| License | Experience |
| --- | --- |
| Microsoft 365 E7 | ✅ Full support |
| Microsoft 365 E5 + Agent 365 | ✅ Full support |
| Microsoft 365 E3 + Defender Suite + Purview Suite + Agent 365 | ✅ Full support |
| Business Premium + Defender Suite + Purview Suite + Agent 365 | ✅ Full support |
| Microsoft 365 F3 + Defender Suite + Purview Suite + Agent 365 | ✅ Full support |
| Microsoft 365 F1 + Defender Suite + Purview Suite + Agent 365 | ✅ Full support |

### ⚠️ ALSO_AI_SECURITY_WINDOWS11_BP — Limited experience- without Agent 365 policies

Package: [`ALSO_AI_SECURITY_WINDOWS11_BP`](ALSO_AI_SECURITY_WINDOWS11_BP)

Use this package for the baseline Windows 11 artifacts and the two BP Conditional Access policies. It excludes policies tagged `A365`.

| License | Experience |
| --- | --- |
| Microsoft 365 E5 | ⚠️ Supports all policies except A365 |
| Microsoft 365 E3 + Defender Suite and/or Purview Suite | ⚠️ Supports all policies except A365 |
| Business Premium + Defender Suite and/or Purview Suite | ⚠️ Supports all policies except A365 |
| Microsoft 365 F3 + Defender Suite and/or Purview Suite | ⚠️ Supports all policies except A365 |
| Microsoft 365 F1 + Defender Suite and/or Purview Suite | ⚠️ Supports all policies except A365 |
| Microsoft 365 E3 | ⚠️ Supports everything except A365 policies and full Defender for Cloud Apps exrpeience (only custom indicators and content filtering)|
| Microsoft 365 Business Premium | ⚠️ Supports everything except A365 policies and full Defender for Cloud Apps exrpeience (only custom indicators and content filtering) |
| Microsoft 365 F3 | ⚠️ Supports everything except A365 policies and full Defender for Cloud Apps exrpeience (only custom indicators and content filtering) |
| Microsoft 365 F1 | ⚠️ All policies except Defender and A365 |

#### Microsoft 365 F3 Limitations

For Microsoft 365 F3, only the following Microsoft Defender security settings are supported:

- Defender Antivirus
- Microsoft Defender Firewall
- Exploit Guard
- Credential Guard
- BitLocker
- BitLocker To Go

All other Defender-related configurations may require additional licensing.

> **Important:** Microsoft 365 F1 supports deployment of Intune configuration and BP Conditional access policies only. Microsoft Defender security policy settings and A365 Conditional access policies included in this repository are not supported with F1 licensing.


---

| Resource | Description |
| --- | --- |
| 📖 **[Public documentation](docs/public/README.md)** | Start with the complete documentation index. |
| 🚀 **[General prerequisites](docs/public/general-prerequisites.md)** | Review licensing, tenant preparation, configure Intune, Defender, Defender for Cloud Apps |
| 🤖 **[Windows requirements](docs/public/platform-and-ai-prerequisites.md)** | Review Windows OS requirements |
| 📦 **[Policy collections](docs/public/policy-collections.md)** | Compare the package contents and select one standalone package. |
| 🔐 **[Conditional Access policy guide](docs/public/conditional-access-policies.md)** | Review the internal-user and Agent 365 Conditional Access policies. |
| 🧩 **[Dependencies and import errors](docs/public/dependencies-and-import-errors.md)** | Resolve referenced groups, compliant-device prerequisites, networks, and concrete Graph errors. |
| 📖 **[Policy naming](docs/public/policy-naming.md)** | Understand the device and Conditional Access naming components. |
| 📂 **[File structure](docs/public/file-structure.md)** | Locate each package and artifact category. |
| 📥 **[How to import](docs/public/how-to-import.md)** | Import a selected package in OFF state and validate it. |
| 🐛 **[Reporting issues](docs/public/reporting-issues.md)** | Report problems without exposing tenant information. |
| 🛡️ **[Security Information](https://github.com/CoC-MS/ALSO-Microsoft-Security-AI-Security-Windows11/tree/main?tab=security-ov-file)** | View Security information
| 📜 **[License](LICENSE)** | Read the repository license. |

---

## 📦 Windows 11 AI Security packages

Each top-level package is complete and standalone. Choose one package; do not combine package folders.

| Package | JSON files | Conditional Access | License mapping |
| --- | ---: | ---: | --- |
| [`ALSO_AI_SECURITY_WINDOWS11_BP`](ALSO_AI_SECURITY_WINDOWS11_BP) | 24 | 2 BP policies | Microsoft 365 Business Premium, E3, E5, F1, or F3 combinations that do not include Agent 365 policy use. |
| [`ALSO_AI_SECURITY_WINDOWS11_E7`](ALSO_AI_SECURITY_WINDOWS11_E7) | 29 | 2 BP + 5 A365 policies | Microsoft 365 E7, or a listed Microsoft 365/Defender/Purview combination with Agent 365. |

> [!WARNING]
> The E7 package is cumulative. The five A365 Conditional Access artifacts exist only in `ALSO_AI_SECURITY_WINDOWS11_E7`; do not copy them into the BP package.

## 🌐 Coverage and capabilities

| Area | BP | E7 |
| --- | ---: | ---: |
| Settings Catalog | 12 | 12 |
| Compliance policies | 4 | 4 |
| BP Conditional Access policies | 2 | 2 |
| A365 Conditional Access policies | 0 | 5 |
| Groups | 4 | 4 |
| Named locations | 1 | 1 |
| Migration table | 1 | 1 |

- Application installation and execution controls, Microsoft Edge controls, Microsoft Store restrictions, and proxy-bypass controls.
- Windows compliance requirements and Conditional Access for corporate-managed devices.
- Defender for Endpoint and Defender for Cloud Apps configuration for non-Microsoft AI service controls.
- E7-only Agent 365 controls for agent identity risk, resource access, compliant devices, and compliant networks.

Policy names describe intent; the JSON settings, assignments, exclusions, dependencies, and tenant configuration determine actual behavior.

## 🚀 Getting started

1. Choose exactly one package using the licensing guide above: [`ALSO_AI_SECURITY_WINDOWS11_BP`](ALSO_AI_SECURITY_WINDOWS11_BP) or [`ALSO_AI_SECURITY_WINDOWS11_E7`](ALSO_AI_SECURITY_WINDOWS11_E7).
2. Review the [general prerequisites](docs/public/general-prerequisites.md), [Windows 11 requirements](docs/public/platform-and-ai-prerequisites.md), [dependencies and error handling](docs/public/dependencies-and-import-errors.md), and [security information](SECURITY).
3. Inspect every selected artifact and map tenant-specific groups, locations, assignments, exclusions, and other references.
4. Follow [How to import](docs/public/how-to-import.md), import Conditional Access policies in **OFF** state, and validate with a controlled pilot before enabling them.
