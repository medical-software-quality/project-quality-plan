This repository contains a project quality plan (PQP) suitable for medical software
compliant with GAMP 5 principles for a modern DevOps context with

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

# Background

Some processes have regulatory requirements over how they are implemented and conducted
(such as GLP and GCP, here denoted GxP).
Software supporting such processes must follow regulations regarding how it is declared
fit for use for such GxP processes.
Such regulations include EMA[^ema][^ema_draft] and FDA[^fda][^fda_draft]
and are broadly covered by [GAMP 5](https://ispe.org/publications/guidance-documents/gamp-5-guide-2nd-edition).
This repository contains a project quality plan (PQP) commensurable with both
GAMP 5 and modern DevOps.

By adopting and following this PQP, its related SOPs and the associated documentation specification,
the software can be declared fit for use in GxP using a quality plan commensurable with GAMP 5.

# Status

This project is in alpha version - do not use it without the supervision of a validation lead
that knows how to present the project in an audit. If you believe that
the procedures do not meet a quality, please raise it as a "bug" on [issues](https://github.com/medical-software-quality/project-quality-plan/issues).

# How to use

## Standard

On your applications's repository (e.g. Gitlab, Github),

1. Apply [this configuration](./configuration.md) to the repository
2. Add [this](https://github.com/medical-software-quality/documentation-as-code) CI check to the repository
3. Link a specific commit hash of this repository's [quality plan](./quality_plan.md) to your README.
4. Create a PR with this change and assign it to a role responsible for the application
   (which constitutes the approval).
5. Have a training session with your team on this plan and corresponding SOPs.
6. Establish a process for new members to have a training session with this plan and corresponding SOPs.
7. Establish a process for yearly refreshers to existing members.

## Advanced

Only do this if you:
* are familiar with GAMP 5 and know what you are doing
* need to modify the PQP in ways specific to your organization's requirements

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

# How to contribute

Create a PR with a justification (e.g. anchored to GAMP 5, FDA or EMA regulation).

# Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, as defined in the license, shall be licensed as above, without any additional terms or conditions.

# References

[^fda]: [Computer Software Assurance for Production and Quality System Software](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/computer-software-assurance-production-and-quality-system-software)

[^fda_draft]: [Draft Computer Software Assurance for Production and Quality System Software](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/computer-software-assurance-production-and-quality-system-software)

[^ema]: [Guidance on Qualification and Classification of Software in Regulation (EU) 2017/745 – MDR and Regulation (EU) 2017/746 – IVDR](https://health.ec.europa.eu/system/files/2020-09/md_mdcg_2019_11_guidance_qualification_classification_software_en_0.pdf)

[^ema_draft]: [Draft Guideline on computerised systems and electronic data in clinical trials](https://www.ema.europa.eu/en/documents/regulatory-procedural-guideline/draft-guideline-computerised-systems-electronic-data-clinical-trials_en.pdf)
