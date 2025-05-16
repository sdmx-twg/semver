# Introduction

This document provides guidelines on versioning in SDMX, including the following:

- Documenting "how-to" version SDMX artefacts following "semantic versioning;"
- Documenting best practices for wildcarding dependencies;
- Documenting best practices around extensions; and
- Documenting best practices for implementing semantic versioning in an existing SDMX environment.

This document is broken down into the following sections:

- [Versioning in SDMX](Versioning%20in%20SDMX.md), which outlines how artefacts can be versioned in SDMX, what semantic versioning is, and how semantic versioning complements the SDMX standard. This document also provides recommendations on [Implementing semantic versioning in an existing SDMX enviroment](Versioning%20in%20SDMX.md#implementing-semantic-versioning-in-an-existing-sdmx-enviroment).
- [General Recommendations for Maintainable Artefacts](./General%20Recommendations%20for%20Maintainable%20Artefacts.md), which details actions applicable to any maintainable artefact and how those actions impact versioning.
- [Artefact Specific Recommendations](./Artefact%20Specific%20Recommendations/), which detail how each action made to a maintainable artefact can impact it's version and what wildcarding considerations should be considered within that artefact.

## Conventions Used in These Guidelines

### Minimum Version Changes

In this document, when we recommend a minimum version change, it means the following:

| Minimum Version Change | Action                                                             |
| :--------------------: | ------------------------------------------------------------------ |
|         Major          | Increment the first digit in the version number                    |
|         Minor          | Increment the first or second digit in the version number          |
|         Patch          | Increment the first or second or third digit in the version number |

### Wildcarding References

When referring to wildcarding, the following conventions are used:

| Level | Meaning | Format                                                                                                                      |
| :---: | ------- | --------------------------------------------------------------------------------------------------------------------------- |
| Patch | X.Y.Z+  | This matches the _latest available stable semantic_ version of an artefact in form of **`x.y.z`** where `x.y.z` >= `X.Y.Z`. |
| Minor | X.Y+.Z  | This matches the _latest available stable semantic_ version of an artefact in form of **`X.y.z`** where `y.z` >= `Y.Z`.     |
| Major | X+.Y.Z  | This matches the _latest available stable semantic_ version of an artefact in form of **`X.Y.z`** where `z` >= `Z`.         |

### Wildcard Reference Icons

The following icons are used to indicate recommendations for wildcard references:

| Icon | Meaning                                                                                  |
| :--: | ---------------------------------------------------------------------------------------- |
|  🟢  | There are no concerns with having a wildcard reference at this level.                    |
|  ⚠️  | Take care in having a wildcard reference at this level; specific concerns will be noted. |
|  🟥  | Do not have a wildcard reference at this level.                                          |
