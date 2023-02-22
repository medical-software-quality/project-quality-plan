This repository contains a project quality plan (PQP) suitable for medical software compliant with
EMA and FDA requirements in a modern DevOps context using
* Agile
* Git version control system
* Continuous integration and continuous deployment (CI/CD)
* A managed git system supporting roles and requests such as github or gitlab

You can find the plan [here](./quality_plan.md). Its version is identified by [semver](https://semver.org/)
git tags on this repository.

The gist of this PQP from a modern CI/CD:
* all configuration (except secrets) is described through code in git (configuration as code)
* all documentation is written in markdown and Gherkin in git (documentation as code)
* `main` points to the current configuration in production except when deployment fails
* changes to `main` can only be done through pull requests

By adopting and following this PQP, its related SOPs and the associated documentation specification,
the software can be declared fit for use in GxP

# How to use

On your applications's repository (e.g. Gitlab, Github),

1. Apply [this configuration](https://github.com/medical-software-quality/release-sop/blob/main/configuration.md) to the repository
2. Add [this](https://github.com/medical-software-quality/documentation-as-code) CI check to the repository
3. Link a specific commit hash of this repository's [quality plan](./quality_plan.md) to your README.
4. Create a PR and assign it to the person responsible for the application.
5. Have a training session with your team on this plan and corresponding SOPs.
6. Establish a process for new members to have a training session with this plan and corresponding SOPs.
7. Establish a process for yearly refreshers to existing members.

# Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the license, shall be licensed as above, without any additional terms or conditions.
