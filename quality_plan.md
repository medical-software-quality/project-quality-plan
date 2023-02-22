# Project quality plan

## Abreviations

* PQP - Project quality plan, this document
* SOP - standard operating procedure
* CI/CD - software that executes a set of instructions related to verification and deployment
  of other software
* DaC - Documentation as code[^1] 

## Roles and responsibilities

* user
  * uses the application
  * reports defects to the projects' ticket
  * supports the team in establishing that defects are correctly addressed
* qualified user
  * has all the responsibilities that a user has
  * supports risk managers in performing risk assessments
  * supports developers in describing requirements
  * may own specific requirements
* risk manager
  * responsible for assessing requirements' impact to risk controls
  * responsible for assessing risks' impact to risk controls
* software developer
  * responsible for developing software
  * responsible for writing tests
  * responsible for writing documentation

## Scope

### In scope

This PQP is intended for medical software guided by [GAMP 5](https://ispe.org/publications/guidance-documents/gamp-5-guide-2nd-edition) within a modern DevOps context using
* Agile
* Git version control system
* continuous integration and continuous deployment (CI/CD)
* A managed git system supporting roles and requests such as github or gitlab

### Out of scope

* This PQP is (currently) _not_ intended for software as a medical device nor software in medical devices.

## Requirements

* A requirement is either critical or it is not described.

* A requirement is automatically critical if it has a direct impact to:
    * Product quality
    * Patient safety
    * Data integrity

    Impact to any of these areas is assessed by a qualified user and risk manager.
    If the requirement does not impact the above, a risk manager decides whether it is
    critical or not.

* There is no distinction between functional and non-functional requirements.

* Requirements are described and identified in the functional specification.

* The functional specification
  is specified and stored according to the DaC specification[^1].

* The functional specification
  has the same lifecycle as the application and it is versioned and released according to the release SOP[^2].

* The functional specification
  is written, reviewed and approved through the software development SOP[^3].

* Requirements _may_ be owned by specific qualified users. When owned, changes
  to requirements must be approved by the owners.

## Risks

* A risk is either relevant or it is not described.

* A risk is relevant when it relates to:
    * Product quality
    * Patient safety
    * Data integrity

    This assessment is conducted together by a qualified user and a risk manager.
    If the risk is unrelated to the above, a risk manager decides whether it is
    relevant or not with support from a qualified user.

* Risks are described, identified and traced in a risk assessment.

* The risk assessment
  is specified and stored according to the DaC specification[^1].

* The risk assessment
  has the same lifecycle as the application and it is versioned and released according to the release SOP[^2].

* The risk assessment
  is written, reviewed and approved through the software development SOP[^3].

* The risk assessment _may_ be owned by some risk managers. When owned, changes
  to risks must be approved by the owners.

* A risk is mitigated by either a design choice, tests or operational monitoring.

## Design

* Design topics are described, identified and traced in a design specification.

* The design specification
  is specified and stored according to the DaC specification[^1].

* The design specification
  has the same lifecycle as the application and it is versioned and released according to the release SOP[^2].

* The design specification
  is written, reviewed and approved through the software development SOP[^3].

* The design specification _may_ be owned by some software developers. When owned, changes
  to risks must be approved by the owners.

## Configuration management

* All configuration items are stored and versioned in the projects' git repository.

* Changes to the controlled production environment are described by the release SOP[^2].

* Access to the controlled production environment is restricted to privileged users; the system
  account used to deploy to production can only be used from the branch `main`.
  Change to these policies can only be done by a (admin) privileged user.

## Software development

* Software development follows the software development SOP[^3].

* All software developers are trained in the software development SOP.

* Changes to the software development SOP[^3] are communicated to the software developers.

## Validation

* All validation activities are performed throught "tests".

* A test is either relevant or it is not described.

* A test is relevant when:
    * it tests a requirement described in the function specification
    * it mitigates a risk described in the risk assessemnt
    * a developer deems it necessary based on the software development SOP[^3].

* Tests are specified, identified, traced and stored in the verification plan.

* The verification plan
  is specified and stored according to the DaC specification[^1].

* The verification plan
  has the same lifecycle as the application and it is versioned and released according to the release SOP[^2].

* The verification plan
  is written, reviewed and approved through the software development SOP[^3].

* Every release requires the verification plan to be executed according to the release SOP[^2].

## Release management

* Releases are executed by the CI/CD (software).

* The CI/CD
  is specified in the release SOP[^2].

* The CI/CD
  is stored in the same git repository as the application.

* The CI/CD
  has the same lifecycle as the application and it is versioned and released according to the release SOP[^2].

* The CI/CD
  is developed, reviewed and approved through the software development SOP[^3].

* The set of merged PRs in the git repository is the set of all releases and constitutes the change log
  of the application.

## Support and maintenance

### User manual and training

* The user manual
  is specified and stored according to the DaC specification[^1].

* The user manual
  has the same lifecycle as the application and it is versioned and released according to the release SOP[^2].

* The user manual
  is written, reviewed and approved through the software development SOP[^3].

### Operations

* The operator manual
  is specified and stored according to the DaC specification[^1].

* The operator manual
  has the same lifecycle as the application and it is versioned and released according to the release SOP[^2].

* The operator manual
  is written, reviewed and approved through the software development SOP[^3].

* Monitoring is described in the operator manual.

* Maintenance changes are no different than any other change and follow the release SOP[^2].

### Retirement

* The retirement plan
  is specified and stored according to the DaC specification[^1].

* The retirement plan
  has the same lifecycle as the application and it is versioned and released according to the release SOP[^2].

* The retirement plan
  is written, reviewed and approved through the software development SOP[^3].

## References

[^1]: [Quality documentation as code specification](https://github.com/medical-software-quality/documentation-as-code/tree/main/documentation/features)

[^2]: [Quality release SOP](https://github.com/medical-software-quality/release-sop/blob/main/sop.md)

[^3]: [Software development SOP](https://github.com/jorgecarleitao/quality-software-development)
