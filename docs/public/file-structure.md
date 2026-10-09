# 📂 File structure

[Public documentation](README.md)

The `ALSO_AI_SECURITY_POLICIES` directory contains pre-generated policy and supporting JSON exports. The current repository structure is:

```text
/
├── ALSO_AI_SECURITY_POLICIES/
│   ├── CompliancePolicies/    4 JSON exports
│   ├── ConditionalAccess/     7 JSON exports
│   ├── Groups/                4 JSON exports
│   ├── NamedLocations/        1 JSON export
│   ├── SettingsCatalog/      12 JSON exports
│   └── MigrationTable.json    Supporting JSON file
└── docs/
    └── public/                Documentation preview
```

| Folder or file | Contents | Review before use |
| --- | --- | --- |
| [ConditionalAccess](../../ALSO_AI_SECURITY_POLICIES/ConditionalAccess/) | Seven policies, including internal-user and Agent 365 controls. | Select only the policies that fit the tenant; import them in **OFF** state. |
| [CompliancePolicies](../../ALSO_AI_SECURITY_POLICIES/CompliancePolicies/) | Four compliance policy exports. | Review the requirements and assignments for managed Windows devices. |
| [Groups](../../ALSO_AI_SECURITY_POLICIES/Groups/) | Four group exports used as Conditional Access support resources. | Review membership and references; the internal-users group is an example. |
| [NamedLocations](../../ALSO_AI_SECURITY_POLICIES/NamedLocations/) | One named-location export. | Confirm the location values and any compliant-network dependencies. |
| [SettingsCatalog](../../ALSO_AI_SECURITY_POLICIES/SettingsCatalog/) | Twelve device configuration policy exports. | Review each setting and its user/device assignment scope. |
| [MigrationTable.json](../../ALSO_AI_SECURITY_POLICIES/MigrationTable.json) | Supporting migration data. | Use with the repository's import workflow; verify destination mappings and references. |

Counts describe the files currently present, not unique destination objects or recommended assignments. Review the JSON content and [policy-specific guidance](conditional-access-policies.md) rather than relying on folder names alone.
