# 🚀 Prerequisites

[Public documentation](README.md)

Review these requirements before selecting exports. The source README describes this solution for **corporate-owned Windows 11 devices**; these exports are starting points and require tenant-specific review.

## Licensing

The source README lists the following minimum licensing combinations:

| Scenario | License listed by the repository |
| --- | --- |
| Baseline policies | Microsoft 365 Business Premium with Defender Suite |
| Agent 365 policies (CA501–CA505) | Agent 365 licence and completed Agent 365 portal onboarding, in addition to the applicable Microsoft 365/Defender licensing |
| Other listed combinations | Microsoft 365 E3 with Defender Suite and Agent 365 for Agent 365 policies; Microsoft 365 E5 with Agent 365; or Microsoft 365 E7 |

Confirm current product names, feature availability, and entitlements with Microsoft before deployment. A policy's filename is not proof that its required features are licensed in a tenant.

## Tenant and service setup

The source README calls out these separate tenant settings:

- Configure Microsoft Intune as the mobile device management (MDM) authority and enable automatic enrollment as appropriate for the environment.
- Enable the Microsoft Intune connection in the Microsoft Defender portal.
- Configure the described Microsoft Defender for Cloud Apps integrations in the Defender portal.
- Ensure **Custom Network Indicators** and **Web Content Filtering** are enabled under Defender for Endpoint settings where required by the intended controls.

These are service-side prerequisites, not all settings are created by importing the policy JSON files. Follow the current Microsoft portal guidance and confirm licensing and onboarding for each service.

## Policy dependencies

- CA204 uses an example internal-users group. Confirm the correct members and scope before use.
- CA205 requires Windows compliance requirements to be configured in Intune before compliant-device access is enforced.
- Agent 365 policies CA501–CA505 require the Agent 365 licence and portal onboarding before import, as stated in the source README.
- Review policy assignments, exclusions, named locations, and any referenced groups against the destination tenant. The included group and location exports may need to be mapped or customized.

See the [Conditional Access policy guide](conditional-access-policies.md) for policy-specific review points.
