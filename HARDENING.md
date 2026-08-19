<!-- markdownlint-disable -->

# Hardening Report: amannn--action-semantic-pull-request/v6.1.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **amannn--action-semantic-pull-request/v6.1.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

All `uses:` references across all workflow files are pinned to mutable tags rather than full 40-character commit SHAs. This exposes the action to supply-chain attacks where a tag could be moved to point to malicious code. Failing references include: `actions/checkout@v5`, `pnpm/action-setup@v4`, `actions/setup-node@v4`, `marocchino/sticky-pull-request-comment@v2`, `Actions-R-Us/actions-tagger@v2`. Each should be pinned to a full SHA digest (e.g. `actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v5`).

Locations:

- `.github/workflows/lint-pr-title-preview-all.yml:15`
- `.github/workflows/lint-pr-title-preview-all.yml:16`
- `.github/workflows/lint-pr-title-preview-all.yml:18`
- `.github/workflows/lint-pr-title-preview-ignoreLabels.yml:16`
- `.github/workflows/lint-pr-title-preview-ignoreLabels.yml:17`
- `.github/workflows/lint-pr-title-preview-ignoreLabels.yml:19`
- `.github/workflows/lint-pr-title-preview-outputErrorMessage.yml:15`
- `.github/workflows/lint-pr-title-preview-outputErrorMessage.yml:16`
- `.github/workflows/lint-pr-title-preview-outputErrorMessage.yml:18`
- `.github/workflows/lint-pr-title-preview-outputErrorMessage.yml:26`
- `.github/workflows/lint-pr-title-preview-outputErrorMessage.yml:40`
- `.github/workflows/lint-pr-title-preview-validateSingleCommit.yml:15`
- `.github/workflows/lint-pr-title-preview-validateSingleCommit.yml:16`
- `.github/workflows/lint-pr-title-preview-validateSingleCommit.yml:18`
- `.github/workflows/lint-pr-title-preview.yml:14`
- `.github/workflows/lint-pr-title-preview.yml:15`
- `.github/workflows/lint-pr-title-preview.yml:17`
- `.github/workflows/lint-pr-title.yml:13`
- `.github/workflows/lint-pr-title.yml:14`
- `.github/workflows/lint-pr-title.yml:16`
- `.github/workflows/release.yml:13`
- `.github/workflows/release.yml:14`
- `.github/workflows/release.yml:16`
- `.github/workflows/tagger.yml:16`
- `.github/workflows/test.yml:12`
- `.github/workflows/test.yml:13`
- `.github/workflows/test.yml:15`
- `.github/workflows/test.yml:26`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all mutable tag references to full commit SHAs across 9 workflow files:
- actions/checkout@v5 → @fbc6f3992d24b796d5a048ff273f7fcc4a7b6c09 # v5
- pnpm/action-setup@v4 → @b906affcce14559ad1aafd4ab0e942779e9f58b1 # v4
- actions/setup-node@v4 → @49933ea5288caeca8642d1e84afbd3f7d6820020 # v4
- marocchino/sticky-pull-request-comment@v2 → @773744901bac0e8cbb5a0dc842800d45e9b2b405 # v2 (2 occurrences in lint-pr-title-preview-outputErrorMessage.yml)
- Actions-R-Us/actions-tagger@v2 → @330ddfac760021349fef7ff62b372f2f691c20fb # v2 (in tagger.yml)
All files updated: lint-pr-title-preview-all.yml, lint-pr-title-preview-ignoreLabels.yml, lint-pr-title-preview-outputErrorMessage.yml, lint-pr-title-preview-validateSingleCommit.yml, lint-pr-title-preview.yml, lint-pr-title.yml, release.yml, tagger.yml, test.yml

