# 🔐 Conditional Access policy guide

[Public documentation](README.md)

This guide summarizes the Conditional Access exports in `ALSO_AI_SECURITY_POLICIES/ConditionalAccess`. Review each JSON's complete conditions, assignments, exclusions, grant controls, and session controls before use; names alone do not describe the full configuration.

> [!IMPORTANT]
> Import Conditional Access policies in **OFF** state. Review the target groups and dependencies, and test the intended sign-in behavior before enabling policies.

| Policy | Export | Purpose described by the repository |
| --- | --- | --- |
| CA204 | [BP-ALSO-CA204-Internals-AllApps-AnyPlatform-Block-UnknownPlatforms](../../ALSO_AI_SECURITY_POLICIES/ConditionalAccess/BP-ALSO-CA204-Internals-AllApps-AnyPlatform-Block-UnknownPlatforms.json) | Blocks internal users from signing in on unsupported or unrecognized device platforms. |
| CA205 | [BP-ALSO-CA205-Internals-AllApps-Windows-Grant-RequireCompliantDevice](../../ALSO_AI_SECURITY_POLICIES/ConditionalAccess/BP-ALSO-CA205-Internals-AllApps-Windows-Grant-RequireCompliantDevice.json) | Requires Windows devices to be compliant before internal users access cloud applications. |
| CA501 | [A365-ALSO-CA501-Agents-AllApps-AnyPlatform-Block-HighRiskAgent](../../ALSO_AI_SECURITY_POLICIES/ConditionalAccess/A365-ALSO-CA501-Agents-AllApps-AnyPlatform-Block-HighRiskAgent.json) | Blocks agent identities Microsoft identifies as high risk from accessing tenant resources. |
| CA502 | [A365-ALSO-CA502-Agents-AllAgentIdentities-AllAgentResources-Block-AllExceptSelected](../../ALSO_AI_SECURITY_POLICIES/ConditionalAccess/A365-ALSO-CA502-Agents-AllAgentIdentities-AllAgentResources-Block-AllExceptSelected.json) | Blocks agent identities by default, allowing only the agents explicitly selected or excluded. |
| CA503 | [A365-ALSO-CA503-Agents-AllAgentUsers-Grant-RequireCompliantDevice](../../ALSO_AI_SECURITY_POLICIES/ConditionalAccess/A365-ALSO-CA503-Agents-AllAgentUsers-Grant-RequireCompliantDevice.json) | Requires compliant devices for agent-user access. |
| CA504 | [A365-ALSO-CA504-Agents-AllAgentUsers-AllResources-Block-RiskyAgents](../../ALSO_AI_SECURITY_POLICIES/ConditionalAccess/A365-ALSO-CA504-Agents-AllAgentUsers-AllResources-Block-RiskyAgents.json) | Blocks agent users Microsoft Entra ID Protection classifies as medium or high risk. |
| CA505 | [A365-ALSO-CA505-Agents-AllAgentUsers-AllResources-Grant-RequireCompliantNetWork](../../ALSO_AI_SECURITY_POLICIES/ConditionalAccess/A365-ALSO-CA505-Agents-AllAgentUsers-AllResources-Grant-RequireCompliantNetWork.json) | Allows agent-user access only from locations connected through the Global Secure Access compliant network. |

### Review before enabling

- CA204 and CA205 use the `ALSO- All Internals` group as an example. Verify its membership or replace it with the intended users before deployment.
- CA205 depends on Windows compliance requirements being configured in Intune. Review the referenced group and any exclusions.
- CA501–CA505 require an Agent 365 licence and Agent 365 portal onboarding, according to the repository's import guidance. Leave them unselected until those prerequisites are met.
- CA502 blocks agent identities by default. Define and verify the intended allowed-agent exclusions before enabling it.
- CA505 depends on a correctly configured compliant network; importing the named location does not configure Global Secure Access.

See [Prerequisites](prerequisites.md) and [How to import](how-to-import.md) before deployment.
