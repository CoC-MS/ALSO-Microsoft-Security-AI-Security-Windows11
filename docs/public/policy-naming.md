# 📖 Policy naming

[Public documentation](README.md)

## 🧩 Naming Components Device policies

| Component | Description |
|-----------|-------------|
| **ALSO** | Company providing the policy template to have a better control |
| **Impact** | Impact level of policy, low (LI), medium (MI) or high (HI) |
| **MinimumLicense** | Minimum Microsoft license required to use the policy |
| **BaselineLevel** | Baseline level of policy, Basic, Advanced |
| **Version** | Policy version, v1.0, v1.1 etc|
| **Windows** | Operating system |
| **MainCategory** | Name of main category, Device Configuration, Device Compliance etc|
| **SubCategory** | Name of sub category, MDE, AV, Disk etc|
| **Settings** | Short settings description |
| **Assignment** | Assignment scope- device (D) or user (U)|

## 🧩 Naming Components Conditional Access policies

| Component | Description |
|-----------|-------------|
| **MinimumLicense** | Minimum Microsoft license required to use the policy |
| **ALSO** | Company providing the policy template to have a better control |
| **CA###** | Unique Conditional Access policy number |
| **Persona** | Target user persona |
| **Apps** | Applications targeted by the policy |
| **Platforms** | Platforms targeted by the policy |
| **AccessControls** | Determines whether access is granted or blocked |
| **SessionControls** | Controls enforced by the policy |

The Conditional Access filenames generally follow:

```text
<MinimumLicense>-ALSO-CA###-<Persona>-<Apps>-<Platforms>-<AccessControls>-<SessionControls>
```

For example:

```text
BP-ALSO-CA205-Internals-AllApps-Windows-Grant-RequireCompliantDevice
```

The filename is a descriptive convention, not a complete configuration specification. Inspect the JSON for actual conditions, grant and session controls, assignments, and exclusions.
