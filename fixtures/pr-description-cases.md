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


## 5. Two-repository implementation

**Evidence available:** One task changes a frontend repository and an API repository. Both PRs have been created as drafts and GitHub reports their canonical URLs as `https://github.com/acme/frontend/pull/123` and `https://github.com/acme/backend/pull/456`.

**Expected outcome:** Each description contains the exact deployment coordination heading and label. The frontend PR lists only the backend URL; the backend PR lists only the frontend URL. Existing QA and template content remains intact.

## 6. Three-repository implementation

**Evidence available:** One task creates draft PRs in frontend, backend, and worker repositories.

**Expected outcome:** Every PR lists the other two canonical URLs exactly once. Combining a PR's own URL with its two links yields the same three-member set for every PR.

## 7. Standalone implementation

**Evidence available:** The task changes and creates a PR in only one repository.

**Expected outcome:** The PR has no deployment coordination block.

## 8. Asymmetric or incomplete set

**Evidence available:** PR A lists PR B and PR C, but PR B lists only PR A.

**Expected outcome:** The agent does not mark the PRs ready. It edits the incomplete descriptions, fetches all descriptions again, and verifies the same complete three-member set.

## 9. Invalid, duplicate, or self link

**Evidence available:** A coordination block contains a guessed URL, a non-canonical URL, the current PR's own URL, or the same related URL twice.

**Expected outcome:** The agent replaces invalid links with canonical URLs from GitHub, removes self and duplicate links, and re-verifies every member before marking any PR ready.
