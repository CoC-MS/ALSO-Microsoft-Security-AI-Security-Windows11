# AI Agent Configuration Templates

This repository is the central place for templates that configure how AI agents
should behave, collaborate, and operate safely across projects.

The templates are intended to make agent behavior consistent and reusable. They
can define:

- agent roles, responsibilities, and areas of expertise;
- instructions, constraints, and expected response style;
- available tools and when an agent may use them;
- workflows for planning, implementation, review, and handoff;
- security, privacy, approval, and escalation requirements;
- project-specific context, coding conventions, and validation steps.

## Template categories

Organize templates by purpose so users can apply only the configuration they
need:

| Category | Purpose |
| --- | --- |
| Base | Shared defaults for every AI agent |
| Role | Behavior for a specific role, such as developer, reviewer, or security analyst |
| Workflow | Instructions for tasks such as planning, coding, testing, or pull request review |
| Tool | Rules for using tools, APIs, terminals, and external services |
| Policy | Security, privacy, compliance, and human-approval requirements |
| Project | Repository-specific architecture, terminology, and engineering conventions |

## Recommended structure

As templates are added, use a structure similar to:

```text
templates/
  base/
  roles/
  workflows/
  tools/
  policies/
  projects/
examples/
```

Each template should document:

1. **Purpose** — what behavior the template controls.
2. **Scope** — which agents, projects, or tasks it applies to.
3. **Inputs** — values that adopters must customize.
4. **Rules** — required behavior and prohibited actions.
5. **Outputs** — the expected response or artifact format.
6. **Validation** — how to verify that the configuration works as intended.

## Applying templates

Start with a base template, then layer more specific configuration on top:

```text
base -> role -> workflow/tool/policy -> project -> task
```

More specific instructions should refine the shared defaults. They should not
silently weaken security, privacy, or approval requirements. If two templates
conflict, resolve the conflict explicitly and document which rule takes
precedence.

Before using a template:

1. Copy it into the target agent or project configuration.
2. Replace all documented placeholders.
3. Remove tools and permissions the agent does not need.
4. Add project-specific commands, constraints, and ownership details.
5. Test the agent with normal, failure, and unsafe-input scenarios.
6. Review and version configuration changes like source code.

## Authoring guidelines

- Write instructions that are specific, testable, and unambiguous.
- Prefer least-privilege access to tools, data, and environments.
- Require human approval for destructive, sensitive, or irreversible actions.
- State how the agent must report uncertainty, errors, and blocked work.
- Define clear boundaries for confidential data and external communication.
- Include validation commands and success criteria where applicable.
- Keep reusable rules in shared templates rather than duplicating them.
- Never include credentials, secrets, personal data, or production tokens.

## Contributing

When adding a template, place it in the appropriate category and include a
working example when its use is not self-evident. Pull requests should explain
the intended agent behavior, the risks addressed, and how the template was
validated.
