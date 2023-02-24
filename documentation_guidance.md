# documentation writing guidance

## Scope

### In scope

This SOP is intended for documentation supporting development activities of medical software
guided by [GAMP 5](https://ispe.org/publications/guidance-documents/gamp-5-guide-2nd-edition).

### Out of scope

This SOP is _not_ intended for use in development of software as a medical device,
nor software in medical devices.

## File names

* files must contain the approriate extension of their format
* the file extension should be lower case
* file names should be lower-cased and words separated by underscores (`_`).

## References

* References are any information that is not present in the document itself
  and instead refer to by a link or document. Such information is subject to change.

* The creation of a reference should be risk-based - consider the impact of a
  change of such information to the future reader.

* These risks are primarily evaluated against the source's ability to preserve 

* When the reference is a URL, consider the risk of future URL changes (e.g. becomes invalid).
  When possible, mitigate such risk by creating the reference against the content's title or
  description. For example:
    * Good: `see e.g. [definition of CTMS](https://example.com)` - if the link becomes invalid the reader
      can find another definition
    * Bad: `see [here](https://example.com) for details` - if the link becomes invalid, the reader
      cannot reconstruct what "here" is in this context.

## Original source

* Files should contain the original source. For example, a diagram created by draw.io
  can be exported to .png but the option to preserve the source should be used to
  easily allow the file to be modified at a later point in time without
  having to reproduce the complete file.

## Language

* Documents should be written in English
* Documents used to communicate to external entities should be written in the language most
  suitable (or required) for such communication (e.g. regulatory authorities)

## Written documents

* unstructured or semi-structured documents whose primary content is English should be written
  in Github-flavoured markdown without HTML.

* Headings must use hash symbols `#`

* The document must start with a h1 heading (`#`) with its title and this must be the only h1 heading

* Documents with references used throughout the document should use the github-flavoured references

* github-flavoured references should be placed on a section at the end of the document (`## References`)
