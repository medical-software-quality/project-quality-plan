# Release standard operating procedure

This SOP allows configuration management and release management of medical software guided by
[GAMP 5](https://ispe.org/publications/guidance-documents/gamp-5-guide-2nd-edition)
within a modern DevOps context using
* Agile
* Git version control system
* continuous integration and continuous deployment (CI/CD)
* A git management system supporting roles and requests such as github or gitlab

By adering to this SOP:
* a software asset can be released and declared fit for use according to its verification plan
* the controlled environment (`prd`) where the asset is declared fit for use remain in control

## Scope

### In scope

* This SOP is intended for development and release of medical software to a controlled environment.

### Out of scope

* This SOP is _not_ intended for development of software _libraries_.
* This SOP is _not_ intended for use in development of software as a medical device,
  nor software in medical devices.

## Process of changing a validated state

### Pre-conditions

* PC1: Changes to `prd` _must only_ be done through this SOP via a trigger from a push to `main`.
* PC2: Commits to `main` must only be done through a request (PR).
* PC3: All PRs _must_ be reviewed and approved by an developer; this developer cannot be the creator of the PR.
* PC4: The review and approval _must_ be done against the exact code that would become the
  new `main` on approval of the PR.
* PC5: In `main`, the git commit message _must_ trace to the corresponding PR.
* PC6: The repository follows the documentation as code specification[^dac].
* PC7: The development on the repository follows a development SOP including but not limited to how:
  * software is developed
  * tests are developed
  * CI/CD is developed
  * documentation is developed
* PC8: The repository contains a CI/CD capable of executing step 2 and 4 below.

### Steps

1. developer 1 creates a PR following the "checklist for PRs" below with changes to the software
   following the repositories development SOP (described in PC7 above).
2. CI/CD executes all tests in the verification plan and presents results in PR
3. developer 2 reviews the PR by verifying that the "checklist for PRs"
   was correctly followed and approves if verification passes.
4. the CI/CD executes the installation script and any post-deployment tests and presents results in PR

#### Checklist for PRs

Confirm that:

* code was developed according to SD SOP[^develop]
* tests were developed according to SD SOP[^develop]
* CI/CD was developed according to SD SOP[^develop]
* Documentation was developed according to SD SOP[^develop]
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

* The PR review and approval constitutes the design review of the change.

* The PR identifier uniquely identifies a release. The PR is also a change record.

* The commit hash in `main` uniquely identifies the source code and configuration.

## References

[^dac]: [documentation as code specification](https://github.com/medical-software-quality/documentation-as-code/tree/main/documentation/features)

[^develop]: [development SOP](./development_sop.md)
