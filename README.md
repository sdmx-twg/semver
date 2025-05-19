# Introduction

This document provides guidelines on versioning in SDMX, including the following:

* Documenting "how-to" version SDMX artefacts following "semantic versioning;"
* Documenting best practices for wildcarding dependencies;
* Documenting best practices around extensions; and
* Documenting best practices for implementing semantic versioning in an existing SDMX environment.

This document is broken down into the following sections:

* [Versioning in SDMX](Versioning%20in%20SDMX.md), which outlines how artefacts can be versioned in SDMX, what semantic versioning is, and how semantic versioning complements the SDMX standard. This document also provides recommendations on [Implementing semantic versioning in an existing SDMX enviroment](Versioning%20in%20SDMX.md#implementing-semantic-versioning-in-an-existing-sdmx-enviroment).
* [General Recommendations for Maintainable Artefacts](./General%20Recommendations%20for%20Maintainable%20Artefacts.md),  which details actions applicable to any maintainable artefact and how those actions impact versioning.
* [Artefact Specific Recommendations](./Artefact%20Specific%20Recommendations/),  which detail how each action made to a maintainable artefact can impact it's version and what wildcarding considerations should be considered within that artefact.

## Changes since SDMX 3.0 guidance

The following sections have been update based on changes to the SDMX standard

The following sections have been update based on changes to the SDMX standard:

* [Categorisation](./Artefact%20Specific%20Recommendations/Artefacts%20with%20Fixed%20Versions/Categorisation.md)
* [DataConstraint](./Artefact%20Specific%20Recommendations/DataConstraint.md)
* [Dataflow](./Artefact%20Specific%20Recommendations/Dataflow.md)
* [DataStructureDefination](./Artefact%20Specific%20Recommendations/DataStructure.md)
* [MetadataConstraint](./Artefact%20Specific%20Recommendations/MetadataConstraint.md)

## Conventions Used in These Guidelines

### Minimum Version Changes

In this document, when we recommend a minimum version change, it means the following:

| Minimum Version Change | Action |
|:----------------------:|--------|
| Major                  | Increment the first digit in the version number |
| Minor                  | Increment the first or second digit in the version number |
| Patch                  | Increment the first or second or third digit in the version number |

### Wildcarding References

When referring to wildcarding, the following conventions are used:

| Level | Format | Meaning |
|:-----:|--------|---------|
| Patch | X.Y.Z+ | This matches the *latest available stable semantic* version of an artefact in form of **`x.y.z`** where `x.y.z` >= `X.Y.Z`. |
| Minor | X.Y+.Z | This matches the *latest available stable semantic* version of an artefact in form of **`X.y.z`** where `y.z` >= `Y.Z`. |
| Major | X+.Y.Z | This matches the *latest available stable semantic* version of an artefact in form of **`X.Y.z`** where `z` >= `Z`. |

### Wildcard Reference Icons

The following icons are used to indicate recommendations for wildcard references:

| Icon | Meaning |
|:----:|---------------|
| 🟢 | There are no concerns with having a wildcard reference at this level. |
| ⚠️ | Take care in having a wildcard reference at this level; specific concerns will be noted. |
| 🟥 | Do not have a wildcard reference at this level. |
