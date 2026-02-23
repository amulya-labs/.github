# .github

Org-wide defaults for **Amulya Labs** — “Priceless Software.”

This repository exists for two reasons:

1) **Organization profile README**
   - `profile/README.md` is shown on the Amulya Labs org “Overview” page.

2) **Default community health files**
   - Files in this repo can act as *defaults* for other repositories in the org (unless they define their own).
   - This keeps contribution expectations, security reporting, and templates consistent across projects.

---

## What belongs here

### Org profile
- `profile/README.md` — public-facing “front page” for the organization

### Default community health files (optional but recommended)
- `CODE_OF_CONDUCT.md`
- `CONTRIBUTING.md`
- `SECURITY.md`
- `SUPPORT.md`
- `.github/ISSUE_TEMPLATE/*`
- `.github/PULL_REQUEST_TEMPLATE.md`
- `.github/FUNDING.yml` (if you use Sponsors)

> Note: If a repo has its own templates under `.github/ISSUE_TEMPLATE`, GitHub will prefer those and won’t use the org defaults.

---

## How changes are used

If a repository *doesn’t* have its own community health file, GitHub will fall back to the version here (in supported locations).  
This helps projects stay consistent without copy/pasting boilerplate into every repo.

---

## Making changes

- Small edits are welcome (typos, clarity, template improvements).
- For anything opinionated (new policy language, behavioral rules, security workflow), open a PR and explain the intent.

---

## Looking for actual projects?

Start here:
- https://github.com/amulya-labs/gha-opencache
- https://github.com/amulya-labs/gha-runnerd
- https://github.com/amulya-labs/claude-code-config
- https://github.com/amulya-labs/bazel-tutorial
