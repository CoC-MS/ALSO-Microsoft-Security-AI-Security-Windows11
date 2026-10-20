# 🧩 Dependencies and import errors

**Disclaimer:** Licensing prerequisites and feature availability listed on this page may be incorrect, incomplete, or outdated. We strongly recommend verifying all licensing information against the latest official Microsoft licensing documentation before making any purchasing or deployment decisions.

[Public documentation](README.md)

Valid JSON can still fail when referenced groups, named locations, device compliance, compliant networks, Agent 365 capabilities, or other tenant objects are absent or not mapped.

## BP-ALSO-CA205-Internals-AllApps-Windows-Grant-RequireCompliantDevice

Requires Windows devices to be compliant before internal users can access cloud applications. Remember to set compliance requirements in Intune for Windows first. Check Windows repo to find compliance templates for Windows. PS: Verify the included group(s) and/or add your custom groups which have all internals in it. ALSO- All Internals is added as an example. This group needs to be imported to Entra, otherwise policy will fail on import with following message:

```text
Failed to invoke MS Graph with URL https://graph.microsoft.com/beta/identity/conditionalAccess/policies (Request ID: df5ea509-9005-47d1-9d00-8852534700ac). Status code: BadRequest. Response message: The server could not process the request because it is malformed or incorrect. Exception: The remote server returned an error: (400) Bad Request
```

---

## BP-ALSO-CA204-Internals-AllApps-AnyPlatform-Block-UnknownPlatforms

Blocks internal users from signing in using unsupported or unrecognized device platforms. PS: Verify the included group(s) and/or add your custom groups which have all internals in it. ALSO- All Internals is added as an example. This group needs to be imported to Entra, otherwise policy will fail on import with following message:

```text
Failed to invoke MS Graph with URL https://graph.microsoft.com/beta/identity/conditionalAccess/policies (Request ID: df5ea509-9005-47d1-9d00-8852534700ac). Status code: BadRequest. Response message: The server could not process the request because it is malformed or incorrect. Exception: The remote server returned an error: (400) Bad Request


```

## Agent 365 Conditional Access policies

## 🤖 Agent Policies

> [!IMPORTANT]
> **All Agent policies (CA501-CA505) require an Agent 365 license to be assigned and Agent 365 portal onboarding to be completed before import. Otherwise, the policies will fail during import and display the following error message.**

```text
"Failed to invoke MS Graph with URL https://graph.microsoft.com/beta/identity/conditionalAccess/policies (Request ID: df32d38d-3943-4a55-bfbc-e1e892358ebb). Status code: BadRequest. Response message: The server could not process the request because it is malformed or incorrect. Exception: The remote server returned an error: (400) Bad Request."
```

## Dependency checklist

| Policy | Dependency to verify |
| --- | --- |
| CA204 | Internal-user group membership, assignments, exclusions, and intended platform behavior. |
| CA205 | Windows compliance policies, internal-user group membership, assignments, and exclusions. |
| CA501–CA504 | Agent 365 licensing and portal onboarding, intended agent identities/users, assignments, and exclusions. |
| CA505 | Agent 365 licensing/onboarding and a correctly configured Global Secure Access compliant network. |

Import supporting groups and named locations first or map them to existing target-tenant objects. Retry a failed policy only after resolving the dependency identified in the import output.
