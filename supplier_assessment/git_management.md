# Supplier assessment of git management system

This assessment was performed according to the supplier assessment for non-medical software[^sop].

## Requirements

The supplier must support
* authentication against the organization's identity provider
* main git functionality:
    * repositories, objects, commits, branches, tags
    * show history of commits
    * git "blame" of individual files
* branch protection of git branches
* role-based access control to actions
* requests to branches (e.g. pull requests, merge requests), including
    * unique identifier of the request
    * require reviewer approval prior to merge
    * reset review on any change
    * require CI checks prior to merge
    * require rebase prior to merge
    * preservation of the request after approval
* functionality to establish provenance of every commit to its request
* a repository-specific issue tracker
* CI/CD functionality:
    * creation and configuration of the pipeline through code
    * configuration of trigger conditions through code
* code ownership configuration as code
* high availability

## Github

This section contains the supplier assessment of [github](https://github.com)
against the above requirements.

This assessment was conducted on 2023-02. The overall conclusion is that the supplier's
product fulfills all requirements and it is fit for purpose.

### Requirements

It was established that the supplier supports all the above requirements with high quality
and performance.

### Risks

The main risks identified are:

#### Backward incompatible changes

The supplier is a SaaS platform with a single version. Therefore, there is a risk
that the supplier will modify the platform resulting in a breakage of requirements.

This risk has a medium impact due how it impacts quality assurance of software developed
in the platform.

This risk was considered low probability due to all the above requirements:
* have been met for +5 years and have not been changed since then
* are widely used by the users of the supplier
* are part of the core product that the supplier offers (and not custom made)

#### Availability

The supplier is a SaaS platform with operations out of our control. Therefore,
there is a risk that the supplier may become unavailable.

The risk has a low impact due to unavailability having low impact to operations.

This risk was deemed low probability due to:
* the track record of the supplier in maintaining high availability of its platform.
* the sound financial status of the supplier

## Gitlab

This section contains the supplier assessment of [gitlab](https://gitlab.com)
against the above requirements.

This assessment was conducted on 2023-02. The overall conclusion is that the supplier's
product fulfills all requirements and it is fit for purpose.

### Requirements

It was established that the supplier supports all the above requirements with high quality
and performance.

### Risks

The main risks identified are:

#### Backward incompatible changes

The supplier is a SaaS platform with a single version. Therefore, there is a risk
that the supplier will modify the platform resulting in a breakage of requirements.

This risk has a medium impact due how it impacts quality assurance of software developed
in the platform.

This risk was considered low probability due to all the above requirements:
* have been met for +5 years and have not been changed since then
* are widely used by the users of the supplier
* are part of the core product that the supplier offers (and not custom made)

#### Availability

The supplier is a SaaS platform with operations out of our control. Therefore,
there is a risk that the supplier may become unavailable.

The risk has a low impact due to unavailability having low impact to operations.

This risk was deemed low probability due to:
* the track record of the supplier in maintaining high availability of its platform.
* the sound financial status of the supplier

## Azure DevOps

This section contains the supplier assessment of
[Azure DevOps](https://azure.microsoft.com/en-us/products/devops)
against the above requirements.

This assessment was conducted on 2023-02. The overall conclusion is that although the supplier's
product fulfills many of the requirements, it is unable to meet important requirements.

### Requirements

It was established that the supplier supports many of the above requirements with high quality
and performance. However, the supplier is unable to meet the following requirements:

#### role-based access control to actions

Although the supplier does support role-based access control to all actions,
the user interface and experience is too difficult to use. During testing, this
resulted in consistent misconfiguration of roles regarding both issue creation
and PR approvals.

#### a repository-specific issue tracker

There is no repository-specific issue tracker. Issues are tracked at the project level.
As a result, it is difficult to keep the list of defects under configuration control.

#### CI/CD functionality: creation and configuration of the pipeline through code

In ADO, there is no CI/CD pipeline associated to a repository; users must
create one and associate it with the repository. During tests, this resulted in often being
unclear what pipeline is running what, resulting in a loss of control over what
is deploying code to the controlled environment.

#### code ownership configuration as code

Code ownership is not declared as code but as a configuration of the platform. This results
in a lack of transparency over who owns which file, as well a significant burden to maintain
code owners. During tests, this resulted in a loss of control over who
owns specific requirements.

### Risks

The main risks identified are:

#### Backward incompatible changes

The supplier is a SaaS platform with a single version. Therefore, there is a risk
that the supplier will modify the platform resulting in a breakage of requirements.

This risk has a medium impact due how it impacts quality assurance of software developed
in the platform.

This risk was considered low probability due to all the above requirements:
* have been met for +5 years and have not been changed since then
* are widely used by the users of the supplier
* are part of the core product that the supplier offers (and not custom made)

#### Availability

The supplier is a SaaS platform with operations out of our control. Therefore,
there is a risk that the supplier may become unavailable.

The risk has a low impact due to unavailability having low impact to operations.

This risk was deemed low probability due to:
* the track record of the supplier in maintaining high availability of its platform.
* the sound financial status of the supplier

## References

[^sop]: [supplier assessment SOP](./sop.md)
