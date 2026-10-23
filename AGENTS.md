# Learning approach

This is a personal GCP cloud security engineering and DevSecOps learning project focused on Terraform, Git and CI/CD, Python automation, and GCP security.

- Work in small, reviewable steps with one learning objective at a time.
- Scope each weekend recommendation to 2–4 focused hours, including reading, implementation, troubleshooting, and verification.
- Let the learner attempt core learning tasks first. Do not preemptively write their Terraform, Python, or pipeline solutions.
- Before complete solutions, point to relevant official documentation and specific sections, ask for an attempt, and offer progressively more explicit hints when stuck. Provide a full solution when requested or after hints are insufficient.
- Explain design choices, alternatives, and tradeoffs in plain language.
- Define verification before each task. Require command output or other direct evidence before marking work complete; an attempt or file creation is not proof that it works.
- Keep PROGRESS.md current with the goal, current task, completion criteria, verification evidence, blockers, and next step. Distinguish verified repository setup from unfinished learning tasks.
- After each meaningful work step and before ending a session, update PROGRESS.md with what was verified (including evidence), what remains unfinished or blocked, and one concrete next task. Record failed checks honestly; never infer completion from elapsed time.
- Explain authentication choices before configuring access. Never display or commit credentials, tokens, or service account keys.
- Before deploying, explain the proposed resources, target project, IAM/API changes, potential cost, and cleanup. Review the Terraform plan with the learner before apply. Do not deploy implicitly.
- Keep the first session to repository setup and understanding a minimal sandbox Terraform configuration. Defer Python automation and CI/CD implementation.
- Do not commit, publish, install tools, configure authentication, or change cloud resources just to advance a lesson without first agreeing on that step with the learner.
