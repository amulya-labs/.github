# Security Badges

Display security badges in your repository README to showcase your security posture.

## GitHub Actions Workflow Badge

Add the workflow badge to show that your security baseline checks are passing:

```markdown
[![Security Baseline](https://github.com/amulya-labs/[REPO_NAME]/actions/workflows/security-baseline.yml/badge.svg)](https://github.com/amulya-labs/[REPO_NAME]/actions/workflows/security-baseline.yml)
```

**Replace `[REPO_NAME]`** with your repository name.

## OpenSSF Scorecard Badge

After your first successful Scorecard run, add this badge to display your OpenSSF security score:

```markdown
[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/amulya-labs/[REPO_NAME]/badge)](https://securityscorecards.dev/viewer?uri=github.com/amulya-labs/[REPO_NAME])
```

**Replace `[REPO_NAME]`** with your repository name.

## Example

Both badges together in your README:

```markdown
## Security

[![Security Baseline](https://github.com/amulya-labs/[REPO_NAME]/actions/workflows/security-baseline.yml/badge.svg)](https://github.com/amulya-labs/[REPO_NAME]/actions/workflows/security-baseline.yml)
[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/amulya-labs/[REPO_NAME]/badge)](https://securityscorecards.dev/viewer?uri=github.com/amulya-labs/[REPO_NAME])
```

---

## What the Badges Mean

- **Security Baseline**: All five security tools (CodeQL, Dependency Review, OSV-Scanner, Gitleaks, Scorecard) ran successfully
- **OpenSSF Scorecard**: Your repository meets OpenSSF security best practices (0-10 scale)

---

## Important Notes

### Scorecard Badge Publishing

After your first successful Scorecard run, the badge may take **24-48 hours** to appear. The badge reflects your latest score once published.

### Gitleaks Pro License (Optional)

If your organization has a Gitleaks Pro license, set it as a secret:

1. **Org-level**: Go to Org Settings → Secrets → New repository secret
   - Name: `GITLEAKS_LICENSE`
   - Value: Your Gitleaks Pro license key

2. **Repo-level**: Go to Repo Settings → Secrets → New repository secret
   - Same name and value

The workflow will automatically use the license if available.

### Weekly Scans

The Security Baseline template runs on a weekly schedule (Sunday at midnight UTC) in addition to push and pull request events. This ensures continuous monitoring even without code changes.
