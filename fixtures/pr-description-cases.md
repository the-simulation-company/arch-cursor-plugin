# PR description behavior cases

Use these cases to verify the installed plugin. Compare whether the resulting PR description contains the expected information; do not require exact headings or wording.

## 1. Route, role, component, and changed behavior

**Evidence available:** The diff changes the `Bulk approve` button on `/admin/orders`. Tests show it is visible only to managers and changes from disabled to enabled when at least one pending order is selected.

**Expected outcome:** The description identifies the route and component, states the before → after behavior, and names the manager role and pending-order setup. It does not invent behavior for other roles or write a full QA suite.

## 2. Navigation and setup inferred from nearby code

**Evidence available:** The edited component is a Slack confirmation panel. The diff does not explain navigation, but its parent route and nearby tests show that users reach it through **Settings → Integrations → Slack** after connecting a workspace.

**Expected outcome:** The description includes that evidenced navigation and connected-workspace setup. It does not guess additional permissions, flags, or variants.

## 3. Internal-only change

**Evidence available:** The PR refactors a server-side cache adapter without changing responses, rendered UI, or externally observable behavior.

**Expected outcome:** The description clearly says there is no browser-visible behavior change and does not fabricate pages, navigation, setup, or QA scenarios.

## 4. Existing template and human-authored content

**Evidence available:** The repository template contains `## Summary`, `## Rollout`, and a checklist. The author has already written a rollout note and checked two items.

**Expected outcome:** The description preserves every template section, the rollout note, and the checklist state while adding useful product context in compatible locations. It does not replace the template with the plugin's suggested headings.
