# Project progress

## Goal

Build a personal GCP cloud security engineering and DevSecOps sandbox while learning Terraform, Git and CI/CD, Python automation, and GCP security through small, verified weekend tasks.

## Current task

Session 1 (2â€“4 focused hours): establish the repository and explain a minimal Terraform configuration for a dedicated sandbox. The learner writes the first configuration after reading the linked official sections in README.md. If tool setup consumes the session, record the blocker and carry validation forward rather than expanding the scope.

## Completion criteria

- Verify repository root, `main` branch, and initial file contents.
- Verify ignore rules exclude Terraform state, local values, and credential artifacts while allowing the dependency lock file.
- Learner explains provider requirements versus provider configuration and identifies the sandbox project ID and region.
- Confirm Terraform and gcloud availability; discuss installation if needed.
- Learner attempts the minimal configuration; review it and verify formatting and validation after initialization.
- Discuss authentication options and record the learner's choice before configuring access.
- Review repository changes together before a first commit.

## Evidence and status

- Ongoing tracking rule: update this file after meaningful work steps and before ending each session with verified evidence, remaining work, and one concrete next task. Failed or unrun checks stay explicitly incomplete.

- Initial inspection: directory listing and file search returned no files; `git status` reported no repository.
- Verified: `git init -b main` succeeded; `git rev-parse --show-toplevel` returned this workspace, and `git symbolic-ref --short HEAD` returned `main`. No commits yet.
- Verified: `git check-ignore` excluded sample state, tfvars, provider cache, and ADC credential paths; the dependency lock path was not ignored.
- PATH discovery found Git. Terraform, gcloud, and Python were not found; installation elsewhere has not been ruled out.
- Verified: AGENTS.md, README.md, PROGRESS.md, and .gitignore were read back after creation. Terraform syntax and cloud behavior remain unverified. `git diff --check` found no tracked diff issues, but the new files are still untracked.
- Terraform configuration, authentication, first commit, and cloud deployment are not complete.

## What remains

- Resolve Terraform and gcloud availability.
- Complete the documentation exercise and learner-written minimal Terraform configuration.
- Run and record formatting, initialization, and validation checks.
- Confirm sandbox details and choose authentication before configuring access.
- Review changes and make the first commit together.

## Blockers / open decisions

- Weekly task brief supplied and corrected by the learner on 2026-10-23: one connected project, 2â€“4 focused hours per recommendation, starting with a Terraform sandbox repository; advance using reported and verified progress only.
- Sandbox project ID, region, existing project/billing status, and authentication preference are not yet known. Do not share secrets.
- Terraform and gcloud availability must be resolved before running their checks.

## Next step

Learner reads the specified Terraform sections, explains the two provider-related blocks, and attempts `infra/sandbox/main.tf` and `variables.tf`. Offer hints before a complete solution. Discuss local user ADC versus impersonation before any login or IAM action.

## Weekly recommendation requirements

Each recommendation must fit 2â€“4 focused hours and include the security problem, one focused coding task, skills practiced, expected deliverable, concrete completion criteria, and one logical next step. Include a few verified official documentation links with specific sections and what to apply, plus one documentation-based exercise. Keep reading tied to the task. Defer unfinished work explicitly; do not infer completion from elapsed time.

Progression: Terraform/Git foundation; branches and merge requests; validation and reviewable plans; secure pipeline authentication; controlled deployment; Python/API verification; troubleshooting and recovery documentation. Add IAM, networking, storage, and audit logging as required. Practice Linux and troubleshooting throughout. Later, implement logging configuration and verify delivery as a public sandbox scenario relevant to Wiz/Google SecOps integration engineering, without employer systems, employer code, or paid security tools.

Reproduce this prompt verbatim in each weekly recommendation and remind the learner to paste it into Codex at the start of the session:

"Help me develop engineering skills while building this project. Work in small steps. Let me attempt core learning tasks first. When Im stuck, start with a hint or diagnostic question. Explain important design choices and require verification of changes. Whenever useful, point me to relevant official documentation and specific sections. Help me learn how to find, read, and apply documentation to answer engineering questions. Explain what to look for, then let me use the documentation before providing a complete solution. Verify links when possible and do not invent documentation URLs."

## GitHub repository setup — 2026-10-23

- Current task: learner creates an empty GitHub repository for this local project; then review files before the first commit and push.
- Verified today: `git status --short --branch` returned `No commits yet on main` and four untracked files: .gitignore, AGENTS.md, PROGRESS.md, README.md. `git remote -v` returned no remotes.
- GitHub connection listed nine accessible repositories; none matched this project. Creation of a project repository remains unverified.
- Completion criteria for this step: verify the new repository URL and empty repository in GitHub. Local linking, first commit, authentication for a push, and uploading files remain unfinished.
- Next task: learner creates `cloud-security-engineering` under `rashawnnn17`, without initializing README, .gitignore, or license, and shares the repository URL for verification. Choose public for a visible portfolio or private while preparing it.

## GitHub repository verified — 2026-10-23

- Verified through the GitHub connector: rashawnnn17/cloud-security-engineering exists, is public, reports size 0 and default branch main, and is accessible through the connection. Branch contents have not been checked separately.
- Reviewed local README.md and .gitignore; they contain learning instructions and exclusion rules, with no credentials observed. AGENTS.md and PROGRESS.md were reviewed earlier in this session.
- Local check still reports no commits on main, four untracked setup files, and no remote.
- Current task / next step: learner stages the four setup files and reviews `git diff --cached --stat` and `git diff --cached --check` before agreeing to the first commit. Success means only the intended four files are staged and the whitespace check passes.
- First commit, remote configuration, local Git authentication, and push remain unfinished. Terraform learning tasks remain unfinished.

## Initial staging verified — 2026-10-23

- Direct verification: `git status --short --branch` showed no commits on main and exactly .gitignore, AGENTS.md, PROGRESS.md, and README.md staged as additions.
- `git diff --cached --stat` reported four files and 165 insertions. `git diff --cached --check` passed with no output (exit code 0).
- This progress entry was added after verification and must be restaged before committing.
- Next task: learner restages PROGRESS.md, makes the agreed first setup commit, and verifies it with `git log -1 --oneline` and `git status --short --branch`. No commit or upload has been performed by the assistant. Remote configuration and push remain unfinished.

## First commit verified — 2026-10-23

- `git log -1 --oneline` returned `2a75754 Initialize cloud security engineering project`.
- `git status --short --branch` returned only `## main`, verifying a clean working tree before this progress update.
- `git remote -v` returned no output: the local repository is not yet linked to GitHub.
- This required progress update creates a new local change after the verified commit; it is not included in 2a75754.
- Next task: learner adds the GitHub HTTPS URL as origin and verifies it with `git remote -v`. Adding a remote stores an address locally and does not authenticate or upload files. Discuss Git authentication before the first push. Upload remains unverified; Terraform tasks remain unfinished.

## GitHub remote verified — 2026-10-23

- `git remote -v` returned origin with https://github.com/rashawnnn17/cloud-security-engineering.git for both fetch and push.
- Latest commit remains 2a75754. Status shows main and only PROGRESS.md modified, as expected from progress tracking.
- Next task: learner commits the progress updates, then runs `git push -u origin main` after understanding HTTPS authentication. Existing Windows Git Credential Manager may use a browser sign-in; the connected GitHub plugin does not prove local Git authentication. No credentials should be pasted into chat or committed.
- Completion criteria: push succeeds and local HEAD matches the main branch on GitHub; upstream tracking is verified. No push has yet been verified.
