# action-workflow-hcp-terraform-workspace

## This repo is now archived as infrastructure has been migrated from HCP Terraform Cloud to using OpenTofu within GitHub Actions

Reusable Workflow for GitHub Actions to ensure an HCP Terraform workspace exists and create the workspace if it does not exist.

## Usage

Use this action in a GitHub Action pipeline to setup a HCP Terraform workspace. Follow the example below to see how to use this action in a GitHub Action.

### Example

In your repository, create a workflow file (e.g., `.github/workflows/deploy.yml`) with the following content:

```yaml
name: Setup Workspace

on:
  workflow_dispatch:

jobs:
  deploy:
    uses: chzylee/action-workflow-hcp-terraform-workspace-setup@v1.0.0
    with:
      tfc_hostname: 'app.terraform.io'
      tfc_organization: 'your-tfc-org'
      tfc_workspace: 'your-workspace'
      tfc_project: 'project-name'
      tfc_token: ${{ secrets.TF_API_TOKEN }}
```

### Inputs

| Name             | Description                       | Required | Example            |
| ---------------- | --------------------------------- | -------- | ------------------ |
| tfc_hostname     | Terraform Cloud hostname          | Yes      | `app.terraform.io` |
| tfc_organization | Terraform Cloud organization name | Yes      | `my-org`           |
| tfc_workspace    | Terraform Cloud workspace name    | Yes      | `my-workspace`     |
| tfc_project      | Terraform Cloud project name      | Yes      | `my-infra-proj`    |
| tfc_token        | Terraform Cloud API token         | Yes      | `secret`           |

---
