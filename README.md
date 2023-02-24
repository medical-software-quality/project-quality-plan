This repository contains a project quality plan (PQP) suitable for medical software compliant with
EMA and FDA requirements in a modern DevOps context using

* Agile
* Git version control system
* Continuous integration and continuous deployment (CI/CD)
* A managed git system supporting roles and requests such as github or gitlab

You can find the plan [here](./quality_plan.md). Its version is
identified by [semver](https://semver.org/) git tags on this repository.

The gist of this PQP from a modern CI/CD:
* all configuration items (except secrets) are described through code in git (configuration as code)
* all documentation is written in [markdown](https://en.wikipedia.org/wiki/Markdown)
  and [Gherkin](https://cucumber.io/docs/gherkin/) in git (documentation as code)
* `main` points to the current configuration in production except when deployment fails
* changes to `main` can only be done through pull requests

By adopting and following this PQP, its related SOPs and the associated documentation specification,
the software can be declared fit for use in GxP.

# How to use

## Standard

On your applications's repository (e.g. Gitlab, Github),

1. Apply [this configuration](./configuration.md) to the repository
2. Add [this](https://github.com/medical-software-quality/documentation-as-code) CI check to the repository
3. Link a specific commit hash of this repository's [quality plan](./quality_plan.md) to your README.
4. Create a PR and assign it to the person responsible for the application
   (which will constitute the approval).
5. Have a training session with your team on this plan and corresponding SOPs.
6. Establish a process for new members to have a training session with this plan and corresponding SOPs.
7. Establish a process for yearly refreshers to existing members.

## Advanced

Only do this if you:
* are familiar with GAMP 5 and know what you are doing
* need to modify the PQP in ways specific to your organization's needs

1. Follow steps 1-2 of standard how to use above
2. Fork this repository to your organization.
3. Modify the SOP and/or PQP to adjust to your organization's:
    * naming conventions
    * roles and responsibilities (e.g. who can approve changes)
    * used platforms (e.g. Gitlab)
4. Link a specific commit hash of that repository's [quality plan](./quality_plan.md) to your README.
5. Follow steps 4-7 of standard how to use above

# License

This repository and all files on it are licensed according to the [LICENSE](LICENSE.md).

# Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the license, shall be licensed as above, without any additional terms or conditions.
