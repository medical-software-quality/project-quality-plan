# Release standard operating procedure

## Background

Some processes in the pharma have regulatory requirements over how they are implemented and conducted
(such as GLP and GCP, here denoted GxP).
Software supporting such processes must follow regulations regarding how it is declared
fit for use for such GxP processes. Such regulations include those by EMA[^1][^2] and FDA[^3][^4],
and are broadly covered by GAMP 5[^5].
This SOP is a concretization of the principles of GAMP 5 in a modern DevOps context.

## Scope

### In scope

This SOP allows configuration management and release management of medical software guided by
GAMP 5 within a modern DevOps context using
* Agile
* Git version control system
* continuous integration and continuous deployment (CI/CD)
* A managed git system supporting roles and requests such as github or gitlab

By adering to this SOP:
* an application can be established fit for intended purpose according to this SOP
* an application can be released and established fit for use according to this SOP
* any changes to the controlled production environment (`prd`) where the application is used remain in control.

### Out of scope

* This SOP is _not_ intended for development of software _libraries_.
* This SOP is (currently) _not_ intended for use in development of software as a medical device,
  nor software in medical devices.

## Process of changing a validated state

### Pre-conditions

* PC1: Changes to `prd` _must only_ be done through this SOP via a trigger from a push to `main`.
* PC2: Commits to `main` must only be done through a request (PR).
* PC3: All PRs _must_ be reviewed and approved by an SME; this SME cannot be the creator of the PR.
* PC4: The review and approval _must_ be done against the exact code that would become the
  new `main` on approval of the PR.
* PC5: In `main`, the git commit message _must_ trace to the corresponding PR.
* PC6: The repository follows the documentation as code specification[^6].
* PC7: The repository follows a software development SOP (SD SOP) linked from its `README.md`
  including but not limited to how:
    * software is developed
    * tests are developed
    * CI/CD is developed
    * documentation is developed

### Steps

1. SME 1 creates a PR following the "checklist for PRs" below with changes to the software
   following the project's SD SOP (described in PC7 above).
2. CI/CD verifies the software in (non-production) environments
    * Static code analysis are executed and results presented in PR
    * Unit-tests are executed and results presented in PR
    * Documentation tests are executed and results presented in PR
    * build and publication (release candidate-versioned) of binaries or artifacts are executed
    * Installation of publication is executed
    * Installation verification is executed and results are presented in PR
    * Integration tests are executed and results are presented in PR
    * Any other optional manual tests are executed and results presented in PR (e.g. as a comment)
    * Any post-deployment tests are executed and results presented in PR
3. Review and approval
    * SME 2 reviews the PR to verify the that "checklist for PRs" was correctly followed and approves
      if that is fulfilled
    * other roles (e.g. release manager) _may_ be required to review the PR to verify that
      other checklists are applied.
4. CI/CD builds and publishes (versioned) binaries or artifacts
5. CI/CD deploys to `prd`
    * Installation to `prd` is executed
    * Any post-deployment tests are executed and results presented in PR (e.g. as a comment)

#### Checklist for PRs

Confirm that:

* code was changed according to SD SOP
* tests were changed according to SD SOP
* CI/CD was changed according to SD SOP
* Documentation was changed according to SD SOP
* the PR contains a descriptive title of the change
* the PR's description contains:
    * a summary of the change
    * the potential impact of the change (e.g. does it require a closing window
      or any manual intervention)
    * any risks of the change (e.g. failed DB migration) and how they were mitigated
      (e.g. through a migration test and a reversible rollback).
    * trace to the issue / change request / RfC, if such setup exists in the project
    * If the PR does not warant a complete verification according to the project's test plan,
      it _must_ provide the tests that may be skipped and a rationale for skipping those tests.

## Notes

* The PR review and approval constitutes the design review of the change. "Other roles" in the review
  are primarily used to establish confidence that the specification meet (user) requirements.

* The PR identifier uniquely identifies a release. The PR is also a change record.

* The commit hash in `main` uniquely identifies the source code and configuration.

## References

[^1]: [Guidance on Qualification and Classification of Software in Regulation (EU) 2017/745 – MDR and Regulation (EU) 2017/746 – IVDR](https://health.ec.europa.eu/system/files/2020-09/md_mdcg_2019_11_guidance_qualification_classification_software_en_0.pdf)

[^2]: [Draft Guideline on computerised systems and electronic data in clinical trials](https://www.ema.europa.eu/en/documents/regulatory-procedural-guideline/draft-guideline-computerised-systems-electronic-data-clinical-trials_en.pdf)

[^3]: [General Principles of Software Validation](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/general-principles-software-validation)

[^4]: [Draft Computer Software Assurance for Production and Quality System Software](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/computer-software-assurance-production-and-quality-system-software)

[^5]: [GAMP 5 Guide 2nd Edition](https://ispe.org/publications/guidance-documents/gamp-5-guide-2nd-edition)

[^6]: [documentation as code specification](https://github.com/medical-software-quality/documentation-as-code/tree/main/documentation/features)
