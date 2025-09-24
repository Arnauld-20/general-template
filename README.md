# DevOps Template (Slim)

Minimal template with **two PR checks** and a **manual apply** workflow.

- PR checks:
  - `Terraform PR (Lint)` → fmt + TFLint
  - `Terraform PR (Plan)` → init/validate/plan (summary in job output, plan artifact uploaded)
- Manual apply:
  - `Terraform (Manual Apply)` → run from Actions after merge

Not included (intentionally):
- Branch protection setup scripts
- Environment approval gates
- Remote state bootstrap and backend-config usage
- Multi-directory matrices
- PR comment polish (no de-dupe, no collapsible details)
- Nightly drift checks
- Slack/Teams notifications

## Quick start
1. Use this repo as a template for new infra repos.
2. Add a valid `AWS_ROLE_ARN` in **Settings → Secrets and variables → Actions**.
3. Work in `terraform/01-s3-bucket/` (sample code), open a PR → see Lint + Plan checks.
4. Merge, then go to **Actions → Terraform (Manual Apply)**, choose `main`, and run.