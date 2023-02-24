# Development standard operating procedure

## Scope

### In scope

This SOP is intended for software, test and software documentation development activities
guided by [GAMP 5](https://ispe.org/publications/guidance-documents/gamp-5-guide-2nd-edition).

### Out of scope

This SOP is _not_ intended for use in development of software as a medical device,
nor software in medical devices.

## Roles and responsibilities

* risk manager
  * assesses requirements' impact to risk controls
* software developer
  * develops software
  * writes tests
  * writes documentation
* qualified user
  * supports risk managers in performing risk assessments
  * supports software developers in describing requirements

## Procedure to change requirements

1. Create a PR on the repository with the new code, tests and documentation, including
   the draft requirement.
2. Request approval of the requirement by the same qualified user (e.g. documented by either a
   PR review or comment on the PR).

## Procedure to assess risk

Risk assessment is performed when reviewing changes to the software:

1. Open the PR
2. Read and understand the changes, including to the risk assessment on the PR
3. If the code differences warrant a change to the risk assessment, request such change to the PR review.
4. If there is a way to mitigate the risk through tests, request such test.

## References

[^1]: [release SOP](./release_sop.md)

[^2]: [documentation as code specification](https://github.com/medical-software-quality/documentation-as-code/tree/main/documentation/features)
