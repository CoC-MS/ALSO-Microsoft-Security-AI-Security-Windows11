# 📥 How to import

[Public documentation](README.md)

Review [Prerequisites](prerequisites.md), the [Conditional Access policy guide](conditional-access-policies.md), and the selected policy files before starting. Import only the resources needed for the intended deployment.

The source README describes importing with [Micke M's Intune Management Tool](https://github.com/Micke-K/IntuneManagement). Follow the tool's current setup, authentication, and permission instructions; UI labels and behavior may change between versions.

> [!WARNING]
> Set Conditional Access policy state to **OFF** during import. The source README also warns that Conditional Access imports can fail when required groups, locations, or other referenced resources are missing.

## Import selected resources

1. Download and extract the repository and the import tool. Sign in to the intended tenant and obtain any required API consent through an authorized administrator.
2. In the tool, open **Bulk > Import** and select the extracted project files.
3. Select the policy categories needed for the planned deployment: Settings Catalog, Compliance Policies, Conditional Access, Groups, and Named Locations. Deselect unrelated resources.
4. Select only the reviewed policies. Do not select CA501–CA505 until the Agent 365 licence and portal onboarding prerequisites are complete.
5. Review the handling of assignments and dependencies. The source README warns that policies may fail if groups or named locations they reference are not imported or otherwise available.
6. Explicitly set Conditional Access policy state to **OFF** before importing. Review the selected tenant, resources, and dependencies, then start the import.
7. Check the tool results and command-window output for errors. Verify the imported objects, references, assignments, and disabled Conditional Access state in the destination tenant.

## Pilot and enable

Before enabling any policy, validate its target users, device scope, application scope, exclusions, licensing, and dependencies. Test changes with an appropriate pilot and confirm expected behavior before expanding deployment.

For policy-specific guidance, see the [Conditional Access policy guide](conditional-access-policies.md). For import or documentation problems, see [Reporting issues](reporting-issues.md).
