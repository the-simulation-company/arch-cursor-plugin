---
name: pr-qa-description
description: Use when Cursor prepares, creates, or edits a GitHub pull request description. Ground the description in the actual change and include the product, navigation, and E2E risk context needed to understand and test its behavior.
---

# PR QA Description

Write or improve the pull request description using evidence from the actual diff, relevant tests, author-provided context, and the repository's PR template.

Capture the useful product context:

- the user-visible change, preferably as before → after behavior;
- the affected pages or UI components and where they appear;
- how a user reaches the changed behavior;
- required setup or state, such as data, role, permissions, account state, or a feature flag;
- behavioral variants only when the implementation or tests show that behavior differs by state, role, or another condition;
- potential failure modes or behavioral boundaries exposed by the change, grounded in the changed code or tests; and
- a concise set of high-value E2E coverage areas for the changed behavior and those risks.

Treat these as information requirements and a preferred extraction block, not a required format for the whole PR description. Follow the repository's PR template, local authoring instructions, and any other applicable PR-writing skill. Preserve human-authored content and every existing section.

Keep the required QA information together whenever the format permits, in this order:

1. If the template already has a dedicated `QA`, `Testing`, `Test plan`, or equivalent section that can hold the information clearly, put it there.
2. Otherwise add a compact `## QA context` section.
3. Only distribute the information across unrelated existing sections when the required format prohibits adding a suitable section or subsection.

Use the following labels when they fit the available evidence and format. When reusing an existing QA section, omit the `## QA context` heading. Keep the selected QA section or block self-contained so downstream extraction does not depend on unrelated sections. Concise repetition of details stated elsewhere is acceptable; do not create multiple QA blocks.

```markdown
## QA context
- User-visible change:
- Affected pages/components:
- How to reach it:
- Required setup/state:
- Behavioral variants:
- E2E considerations:
```

Omit irrelevant or empty labels. Exact UI copy, product rationale, test evidence, or a scope note such as "No browser-visible behavior" may be included when it materially clarifies the change. Keep E2E considerations at the behavior level: identify the flow, state transition, permission boundary, integration boundary, or failure path worth validating. Do not turn them into detailed test scripts or a complete set of test goals; downstream goal creation decides the exact new or revised goals against the existing goal inventory.

Do not invent product behavior, navigation, setup, variants, failure modes, or E2E coverage. Infer a risk only when it follows from the changed control or data flow, an evidenced behavioral boundary, or a nearby test, and present it as something worth validating rather than as confirmed product behavior. Before treating navigation or setup as unknown, keep tracing the relevant routes, component callers, authentication and role checks, feature flags, fixtures, tests, seed data, and nearby documentation. Leave a short, clearly marked question for the author only when the answer depends on inaccessible code or data, unavailable environment configuration, or product intent that is not represented in the repository; state exactly what information is missing. Do not add exhaustive file lists, generic implementation summaries, a complete QA scenario inventory, or an executable goal set.
