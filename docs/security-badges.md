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
