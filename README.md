# test-repository-2

This repository demonstrates how to consume reusable GitHub Actions workflows from the `gha-actions` repository using a GitHub App–based automation model.

All automated changes in this repository are executed using GitHub App installation tokens (short-lived, generated per run), ensuring clear system identity, least-privilege access, and improved auditability.

## Available Trigger Workflows

### 1. Trigger Release Creation
**Path:** `.github/workflows/trigger-create-release.yml`  
Manually triggers the reusable `create-release` workflow from `gha-actions` to create a GitHub release for a specified tag.

**Input**
- `tag` (string, default: `v0.0.1`)

---

### 2. Trigger File Creation, PR, and Merge
**Path:** `.github/workflows/trigger-create-file-pr-merge.yml`  
Manually triggers the reusable `create-file-pr-merge` workflow from `gha-actions` to:
- create a file on a new branch,
- open a pull request,
- merge it into the target branch, and
- clean up the temporary branch.

**Inputs**
- `filename` (string)
- `file_content` (string)
- `base_branch` (string, default: `main`)
