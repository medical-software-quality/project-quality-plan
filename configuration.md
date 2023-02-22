# GitHub

Below is a configuration for Github repository and its `main` branch
that fulfills the preconditions PC1-PC5 of [the SOP](./sop.md).
The configuration is written as a JSON usable as a patch in the
[Github REST API](https://docs.github.com/en/rest).

## Repository configuration

```json
{
    "allow_squash_merge": true,
    "allow_merge_commit": false,
    "allow_rebase_merge": false,
    "web_commit_signoff_required": true,
    "squash_merge_commit_title": "PR_TITLE",
    "squash_merge_commit_message": "PR_BODY"
}
```

## Configuration of branch `main`

```json
{
    "required_status_checks": {
        "strict": true,
    },
    "enforce_admins": true,
    "required_pull_request_reviews": {
        "dismiss_stale_reviews": true,
        "require_code_owner_reviews": true,
        "required_approving_review_count": 2,
        "require_last_push_approval": true
    },
    "required_linear_history": true,
    "allow_force_pushes": false,
    "allow_deletions": false,
    "block_creations": true
}
```

## Other configurations

It is recommended that

* no SME is administrator of the repository, so that configurations
  cannot be changed by the team. This mitigates the risk of force pushes to `main` and other
  changes that would result in a deviation of the pre-conditions of this SOP.
* Credentials to deploy to `prd` are restricted to only be usable
  when the CI/CD is running from `main`. This mitigates the risk that misconfigurations of a CI/CD
  trigger would result in uncontrolled deployments to `prd`.
* the repositories, including PRs comments and CI logs and git repository are backed-up
  on a frequent basis to mitigate the risk of a destructive action on the repository
  to erase relevant development and release metadata.
* the directory `documentation/` is [code-owned](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)
  by the person representing the application to inspections. This mitigates the risk that
  the representative is not familiar with the project's specifics and the inspection is poorly executed.
* Create a PR template in the repository with:
  * the "Checklist for PRs" from the SOP
  * other checklists in the SD SOP
  This mitigates the risk of SMEs forgetting items from the checklist.
