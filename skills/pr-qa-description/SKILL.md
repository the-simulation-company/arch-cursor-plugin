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

Preserve human-authored content and every repository-template section. Fit the context into the existing template. When no template determines the structure, use only the headings that help:

```markdown
## User-visible change
## UI components
## How to reach it
## Setup
## Behavioral variants
## E2E considerations
```

Omit irrelevant or empty headings. Exact UI copy, product rationale, test evidence, or a scope note such as "No browser-visible behavior" may be included when it materially clarifies the change. Keep E2E considerations at the behavior level: identify the flow, state transition, permission boundary, integration boundary, or failure path worth validating. Do not turn them into detailed test scripts or a complete set of test goals; downstream goal creation decides the exact new or revised goals against the existing goal inventory.

Do not invent product behavior, navigation, setup, variants, failure modes, or E2E coverage. Infer a risk only when it follows from the changed control or data flow, an evidenced behavioral boundary, or a nearby test, and present it as something worth validating rather than as confirmed product behavior. Before treating navigation or setup as unknown, keep tracing the relevant routes, component callers, authentication and role checks, feature flags, fixtures, tests, seed data, and nearby documentation. Leave a short, clearly marked question for the author only when the answer depends on inaccessible code or data, unavailable environment configuration, or product intent that is not represented in the repository; state exactly what information is missing. Do not add exhaustive file lists, generic implementation summaries, a complete QA scenario inventory, or an executable goal set.
