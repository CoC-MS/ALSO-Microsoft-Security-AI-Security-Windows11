# 📦 Policy collections

[Public documentation](README.md)

Choose exactly one standalone package. E7 is cumulative and contains every BP artifact plus the five A365 Conditional Access policies.

| Collection | BP | E7 |
| --- | ---: | ---: |
| Settings Catalog | 12 | 12 |
| Compliance policies | 4 | 4 |
| BP Conditional Access policies | 2 | 2 |
| A365 Conditional Access policies | 0 | 5 |
| Groups | 4 | 4 |
| Named locations | 1 | 1 |
| Migration table | 1 | 1 |
| **Total JSON files** | **24** | **29** |

## `ALSO_AI_SECURITY_WINDOWS11_BP`

Use the BP package for the baseline Windows 11 security artifacts without Agent 365 policies.

## `ALSO_AI_SECURITY_WINDOWS11_E7`

Use the E7 package when the tenant is licensed and onboarded for Agent 365. It includes the complete BP collection and these five E7-only A365 policies:

- `A365-ALSO-CA501-Agents-AllApps-AnyPlatform-Block-HighRiskAgent.json`
- `A365-ALSO-CA502-Agents-AllAgentIdentities-AllAgentResources-Block-AllExceptSelected.json`
- `A365-ALSO-CA503-Agents-AllAgentUsers-Grant-RequireCompliantDevice.json`
- `A365-ALSO-CA504-Agents-AllAgentUsers-AllResources-Block-RiskyAgents.json`
- `A365-ALSO-CA505-Agents-AllAgentUsers-AllResources-Block-RequireCompliantNetWork.json`

The first four A365 artifacts were already present in this repository and match Conditional Access `main`. CA505 is copied byte-for-byte from `CoC-MS/ALSO-Microsoft-Security-Conditional-Access` commit `b4658f7d034cfc9818d6b053baf455171fd8810c`, Git blob `1585e1406ab751110e511500e39594e53e6c6338`, SHA-256 `e884017a8b50439bb0fb007588b0e58b62d8fc85f83b02e5b121f55c85ffdad6`.

> [!WARNING]
> Do not combine package folders. Review licensing, settings, dependencies, assignments, and exclusions before use, and import Conditional Access policies in **OFF** state.
