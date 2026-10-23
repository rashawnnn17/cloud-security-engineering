# GCP cloud security engineering sandbox

Build practical skills in Terraform, Git and CI/CD, Python automation, and GCP security through small, verified weekend exercises.

## Session 1: local foundation

Budget 2–4 focused hours, including reading, tool setup, writing the minimal configuration, and verification. If tool setup blocks validation, record the evidence and continue next session. CI/CD and deployment belong to later sessions.

Start with an existing dedicated sandbox project once its project ID and billing context are confirmed. Creating a GCP project, enabling APIs, assigning IAM roles, and deploying resources are separate cloud changes to discuss first.

### Read before writing Terraform

Read HashiCorp's [Build infrastructure](https://developer.hashicorp.com/terraform/tutorials/gcp-get-started/google-cloud-platform-build), specifically **Write configuration**, **Terraform Block**, and **Providers**. The tutorial also creates resources; stop before its resource and apply steps for this lesson.

Read [Provider requirements](https://developer.hashicorp.com/terraform/language/providers/requirements), specifically **Source Addresses** and **Version Constraints**.

Your first exercise: create `infra/sandbox/main.tf` declaring the `hashicorp/google` provider with a deliberate version constraint, then configure the provider's project and region using string input variables. Declare those variables in `variables.tf`. Choose the Terraform CLI constraint after checking the installed version. Leave out resources, data sources, credentials, and a remote backend for this exercise.

Explain in your own words:

1. How does `required_providers` differ from `provider "google"`?
2. Why use a project ID rather than a display name?
3. Why does declaring a provider not itself create infrastructure?
4. Why should `.terraform.lock.hcl` be committed while state and local credentials stay out of Git?

Hints: provider requirements identify the plugin; provider configuration supplies its settings. Project and region variables make the target explicit. A zone is needed only for zonal work. All `.tf` files in the same directory form one configuration; their filenames are organizational choices.

### Authentication decision (discussion first)

Read Google's [Authentication for Terraform](https://docs.cloud.google.com/docs/terraform/authentication), sections **Authenticate using a user account**, **Authenticate using service account impersonation**, and **Authenticate when running Terraform outside of Google Cloud**.

- Local user Application Default Credentials (ADC): simplest starting choice for a personal sandbox; Terraform acts with your user's permissions. ADC saves credentials locally. CLI sign-in and ADC setup are distinct.
- Service account impersonation: use a dedicated, narrowly authorized identity with short-lived tokens. Requires an existing service account and permission to impersonate it; creating it or granting roles changes cloud IAM.
- External CI/CD later: Workload Identity Federation exchanges the runner's identity for short-lived access. Agree on the CI platform and trust restrictions before configuring it.
- Service account JSON keys: long-lived secret material; avoid for this project when keyless options work.

Recommendation: discuss user ADC for initial local learning, then impersonation for scoped deployment access and federation for CI. Do not configure any of these until the learner chooses the approach.

### Verification sequence after your attempt

First confirm installed tools and review the files. From `infra/sandbox`, run `terraform fmt -check`, then `terraform init -backend=false`, then `terraform validate`. Initialization downloads providers and writes local working files and a dependency lock file; discuss that step before running it. These checks do not prove cloud access or correct IAM. No plan or apply is needed for the first syntax exercise.

Keep state local for now, outside Git; discuss secure remote state before managing real infrastructure or sharing runs. Review `git status` and `git diff --check` before making a first commit together.
