# Documentation management system

## Storage

* Approved documents are stored by git in the git management system[^1].

* Documents are stored and organized in git repositories and are uniquely identified by
  * repository: the git repository it is located at
  * path: the path of the document within the repository

## Versioning

* A specific version of all files in git is a git "commit". A commit is composed by
    * The who (author of the commit)
    * The what (the content of all files in all directories in the repository)
    * The when (date that the commit was made)
    * The context (a textual description of the commit)
    * The provenance (the hash of the _previous_ commit)

* A commit is uniquely identified by its hash (e.g. `ag12fkf...`).

* Documents are versioned after their commit hash. The tuple `(repository, path, hash)`
  uniquely identifies a document and its version.

## Writing, review and approval

* Documents are created and modified according to the documentation writing guidance[^2].
* Documents are reviewed, approved and released according to the release SOP[^3] where
  the application represents the document and "validated state" is the approval.

## Approved versions

* The currently approved version of a document is the commit hash that the git branch `main` points to
* Previous versions of approved documents are stored in git and can be retrieved
  from the provenance of the commit.
* The approver of every version can be retrieved from the approval process linked in context.

## References

[^1]: [Github management system](https://github.com/)

[^2]: [documentation writing guidance](./documentation_sop.md)

[^3]: [release SOP](./release_sop.md)
