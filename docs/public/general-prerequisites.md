# 🚀 General prerequisites

[Public documentation](README.md)

Review these requirements before selecting a package. This solution is for corporate-owned Windows 11 devices, and every export requires tenant-specific review.

## Licensing

Use the [licensing guide in the main README](../../README.md#windows-11-ai-security-licensing-guide) and choose exactly one package:

- `ALSO_AI_SECURITY_WINDOWS11_BP` for the baseline artifacts without Agent 365 policies.
- `ALSO_AI_SECURITY_WINDOWS11_E7` for the cumulative package, including the five A365 Conditional Access policies.

Confirm current product names, feature availability, and entitlements with Microsoft before deployment. A policy filename is not proof that its required features are licensed in a tenant.

## Tenant preparation

- Use an account authorized to review and import Intune and Conditional Access configuration.
- Preserve emergency-access accounts and test exclusions before enabling Conditional Access.
- Review every assignment, exclusion, group, named location, application, and tenant-specific identifier.
- Configure Windows compliance requirements before using compliant-device Conditional Access.
- Complete Agent 365 licensing and portal onboarding before importing CA501–CA505.

## Deployment readiness

- Download one standalone package only; do not combine BP and E7 folders.
- Review JSON settings and dependencies before import.
- Import Conditional Access policies in **OFF** state.
- Validate with a controlled pilot, sign-in evidence, device compliance, and expected access behavior before broader deployment.

Continue with [Platform and AI prerequisites](platform-and-ai-prerequisites.md) and [Dependencies and import errors](dependencies-and-import-errors.md).
