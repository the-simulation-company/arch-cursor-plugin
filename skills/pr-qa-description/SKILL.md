---
name: pr-qa-description
description: Use when Cursor prepares, creates, or edits a GitHub pull request description. Ground the description in the actual change and include the product and navigation context needed to understand its behavior.
---

# PR QA Description

Write or improve the pull request description using evidence from the actual diff, relevant tests, author-provided context, and the repository's PR template.

Capture the useful product context:

- the user-visible change, preferably as before → after behavior;
- the affected pages or UI components and where they appear;
- how a user reaches the changed behavior;
- required setup or state, such as data, role, permissions, account state, or a feature flag; and
- behavioral variants only when the implementation or tests show that behavior differs by state, role, or another condition.

Preserve human-authored content and every repository-template section. Fit the context into the existing template. When no template determines the structure, use only the headings that help:

```markdown
## User-visible change
## UI components
## How to reach it
## Setup
## Behavioral variants
```

Omit irrelevant or empty headings. Exact UI copy, product rationale, test evidence, or a scope note such as "No browser-visible behavior" may be included when it materially clarifies the change.

Do not invent product behavior, navigation, setup, variants, edge cases, or test scenarios. Before treating navigation or setup as unknown, keep tracing the relevant routes, component callers, authentication and role checks, feature flags, fixtures, tests, seed data, and nearby documentation. Leave a short, clearly marked question for the author only when the answer depends on inaccessible code or data, unavailable environment configuration, or product intent that is not represented in the repository; state exactly what information is missing. Do not add exhaustive file lists, generic implementation summaries, or a complete QA scenario inventory.
