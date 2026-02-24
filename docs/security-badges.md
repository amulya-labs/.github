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

---

## Customizing the Security Baseline

### CodeQL Query Suites

When customizing CodeQL for your repository, choose the appropriate query suite:

- **`security-and-quality` (default)**: Recommended for most projects. Includes security checks plus code quality rules. Faster analysis.
- **`security-extended`**: For sensitive projects (authentication, cryptography, data handling). More comprehensive but slower.

Edit your workflow to change:
```yaml
codeql:
  uses: amulya-labs/.github/.github/workflows/reusable-codeql.yml@main
  with:
    languages: '["python"]'
    query-suite: security-extended
```

### Languages and Build Mode

For compiled languages (C, C++, Go, Java), adjust the `build-mode`:

- **`autobuild` (default)**: Automatic detection and building. Works for most projects.
- **`manual`**: For complex builds or monorepos. You'll need to add custom build steps.

### Dependency Severity Threshold

Adjust how strictly dependencies are reviewed:

```yaml
dependency-review:
  uses: amulya-labs/.github/.github/workflows/reusable-dependency-review.yml@main
  with:
    fail-on-severity: critical  # Options: critical, high, moderate, low
```

### Private Repository Requirement for Scorecard

The OpenSSF Scorecard **badge publishing** requires:
- Public repository (scores published to securityscorecards.dev)
- `publish-results: true` in the workflow
- Valid OIDC token (auto-provided by GitHub)

**For private repositories:** Set `publish-results: false` in your workflow. Your repository will still run all security checks; the public badge just won't appear.

```yaml
scorecard:
  uses: amulya-labs/.github/.github/workflows/reusable-scorecard.yml@main
  with:
    publish-results: false  # Set to false for private repos
```
