# 📖 Policy naming

[Public documentation](README.md)

The source README describes these components for Conditional Access policy names:

```text
<MinimumLicense>-ALSO-CA###-<Persona>-<Apps>-<Platforms>-<AccessControls>-<SessionControls>
```

For example:

```text
BP-ALSO-CA205-Internals-AllApps-Windows-Grant-RequireCompliantDevice
```

| Component | Meaning | Example |
| --- | --- | --- |
| `MinimumLicense` | Minimum license classification in the source name. Confirm actual feature entitlements. | `BP`, `A365` |
| `ALSO` | Template provider. | `ALSO` |
| `CA###` | Conditional Access policy identifier. | `CA204`, `CA501` |
| `Persona` | Intended identity scope. | `Internals`, `Agents` |
| `Apps` | Intended application/resource scope. | `AllApps`, `AllAgentUsers` |
| `Platforms` | Intended platform scope. | `AnyPlatform`, `Windows`, `AllAgentResources` |
| `AccessControls` | Intended access action. | `Block`, `Grant` |
| `SessionControls` | Descriptive suffix for the policy control or purpose. | `UnknownPlatforms`, `RequireCompliantDevice`, `HighRiskAgent` |

The filename is a descriptive convention, not a complete configuration specification. Inspect the JSON for actual conditions, grant and session controls, assignments, and exclusions. See the [Conditional Access policy guide](conditional-access-policies.md).
