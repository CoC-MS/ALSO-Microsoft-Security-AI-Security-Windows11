# 📂 File structure

[Public documentation](README.md)

The repository exposes two standalone top-level packages:

```text
/
├── ALSO_AI_SECURITY_WINDOWS11_BP/   24 JSON files
│   ├── CompliancePolicies/           4
│   ├── ConditionalAccess/            2
│   ├── Groups/                       4
│   ├── NamedLocations/               1
│   ├── SettingsCatalog/             12
│   └── MigrationTable.json           1
├── ALSO_AI_SECURITY_WINDOWS11_E7/   29 JSON files
│   ├── CompliancePolicies/           4
│   ├── ConditionalAccess/            7
│   ├── Groups/                       4
│   ├── NamedLocations/               1
│   ├── SettingsCatalog/             12
│   └── MigrationTable.json           1
└── docs/
    └── public/
```

| Folder or file | Contents | Review before use |
| --- | --- | --- |
| `ConditionalAccess` | Two BP policies in both packages; five additional A365 policies in E7 only. | Select only policies that fit the tenant; import them in **OFF** state. |
| `CompliancePolicies` | Four compliance policy exports. | Review requirements and assignments for managed Windows devices. |
| `Groups` | Four group exports used as Conditional Access support resources. | Review membership and references; the internal-users group is an example. |
| `NamedLocations` | One named-location export. | Confirm location values and compliant-network dependencies. |
| `SettingsCatalog` | Twelve device configuration policy exports. | Review each setting and its user/device assignment scope. |
| `MigrationTable.json` | Supporting migration data. | Verify destination mappings and references. |

Counts describe files, not unique destination objects or recommended assignments. Choose exactly one package and review the [policy collections](policy-collections.md).

## Previously authored file-structure wording

## 📂 File Structure

All files are organized into categories

```text
/ALSO-Microsoft-Security-WindowsServer
├── ALSO_AI_SECURITY_POLICIES/SettingsCatalog
12 SettingsCatalog policies
├── ALSO_AI_SECURITY_POLICIES/CompliancePolicies
4 Compliance policies
├── ALSO_AI_SECURITY_POLICIES/ConditionalAccess
7 Conditional Access policies
├── ALSO_AI_SECURITY_POLICIES/Groups
4 security groups for Conditional Access policies
├── ALSO_AI_SECURITY_POLICIES/NamedLocations
1 Named Location for Conditional Access policy

```


---
