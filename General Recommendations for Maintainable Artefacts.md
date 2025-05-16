# General Recommendations for Maintainable Artefacts

In SDMX maintainable artefacts are artefacts which have an agency, ID, and version. As the only artefacts with a version in SDMX, these artefacts are the focus on this document. General recommendations related to all maintainable artefacts can be found below.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Change agencyID | N.A. | This is now a new artifact with its own versioning. |
| Change id | N.A. | This is now a new artifact with its own versioning. |
| Change version | Depends | If the change is a patch, minor, or major change will be dictated by what is entered as the version. |
| Change URN | N.A. | The URN is formed from the Namespace, Agency, ID, and Version and should not change on its own. |
| Change Name | Patch | Changing the Name includes add or removing names in different languages as well as changing an existing name. |
| Change Description | Patch | Changing the Description includes add or removing Descriptions in different languages as well as changing an existing Description. |
| Change URI | Patch | Changing the URI includes add or removing the URI as well as changing its value. |
| Change Link | Patch | Changing the Link includes add or removing the Link as well as changing any of its attributes. |
| Change validFrom | Patch | Changing the validFrom includes add or removing the validFrom attribute as well as changing it to a different value. |
| Change validTo | Patch | Changing the validTo includes add or removing the validTo attribute as well as changing it to a different value. |
| Any annotation change | No Impact | See [below](#annotations) |
| Change isExternalReference | N.A. | This is a flag to say if the artefact is maintained within the system or not, changing it cannot impact the version.   |
| Change serviceURL | N.A. | This is part of a reference to an artefact you are not maintaining, so you can't modify the version by changing this value. |
| Change structureURL | N.A. | This is part of a reference to an artefact you are not maintaining, so you can't modify the version by changing this value. |

## Annotations

An annotation is just a construct that contains user or organisation-specific metadata. While an annotation may have an impact on a given system’s processing of a structure, they are in general not standardized across organisations. [The Guidelines on the use of SDMX Annotations](https://sdmx.org/wp-content/uploads/Guidelines-on-the-use-of-SDMX-Annotations-2.0.docx) introduced some standardisations with an aim to improve interoperability of Annotations between SDMX-compliant organisations. Even in the case where an annotation is standardised, frequent changing of annotations values makes tying version changes of artifacts to them undesirable. While the maintainer of an artefact may decide to increase the version number due to an annotation change, the recommendation is that such an increase is voluntary.

## Changing an artefact reference

When changing a reference to an artefact, you can change the agency, ID, or version of the referenced artefact. When you change the agency or ID you are fundamentally changing what artefact you are referencing. More common is changing the version of the referenced artefact, such as changing the reference a Dataflow makes to a Data Structure Definition to use the latest version.

| Action                                | Minimum Version Change |
|---------------------------------------|:----------------------:|
| Change artefact reference agency      |          Major         |
| Change artefact reference ID          |          Major         |
| Change artefact reference version     |        See below       |

Changing the version referenced falls into one of these five categories:

* [Change static reference to a new static reference](#change-static-reference-to-a-new-static-reference)
* [Replace a wildcard reference with a static reference](#replace-a-wildcard-reference-with-a-static-reference)
* [Use a wildcard reference at patch level](#use-a-wildcard-reference-at-patch-level)
* [Use a wildcard reference at minor level](#use-a-wildcard-reference-at-minor-level)
* [Use a wildcard reference at major level](#use-a-wildcard-reference-at-major-level)

The recommendations around each category of version changes are outlined in the sections below, note there are some artefacts where these recommendations are modified, for example [ReportingTaxonomy](./Artefact%20Specific%20Recommendations/ReportingTaxonomy.md) but these cover the majority of artefact references.

### Change static reference to a new static reference

An example of removing a wildcard reference is changing a reference from 1.2.0 to 1.3.2.

| Action                                | Minimum Version Change |
|---------------------------------------|:----------------------:|
| Resultant version decreases and differs at major level | Major |
| Resultant version decreases and differs at minor level | Major |
| Resultant version decreases and differs at patch level | Patch |
| Resultant version unchanged                            | N.A.  |
| Resultant version increases and differs at patch level | Patch |
| Resultant version increases and differs at minor level | Minor |
| Resultant version increases and differs at major level | Major |

### Replace a wildcard reference with a static reference

An example of removing a wildcard reference is changing a reference from 1.0+.0 to 1.3.2.

| Action                                | Minimum Version Change |
|---------------------------------------|:----------------------:|
| Resultant version decreases and differs at major level | Major |
| Resultant version decreases and differs at minor level | Major |
| Resultant version decreases and differs at patch level | Patch |
| Resultant version unchanged                            | Minor |
| Resultant version increases and differs at patch level | N.A.  |
| Resultant version increases and differs at minor level | Minor |
| Resultant version increases and differs at major level | Major |

### Use a wildcard reference at patch level

An example of adding a wildcard reference at the minor level is setting the version to 1.0.0+.

| Action                                | Minimum Version Change |
|---------------------------------------|:----------------------:|
| Resultant version decreases and differs at major level | Major |
| Resultant version decreases and differs at minor level | Major |
| Resultant version decreases and differs at patch level | N.A.  |
| Resultant version unchanged                            | Patch |
| Resultant version increases and differs at patch level | Patch |
| Resultant version increases and differs at minor level | Minor |
| Resultant version increases and differs at major level | Major |

### Use a wildcard reference at minor level

An example of adding a wildcard reference at the minor level is setting the version to 1.0+.0.

| Action                                | Minimum Version Change |
|---------------------------------------|:----------------------:|
| Resultant version decreases and differs at major level | Major |
| Resultant version decreases and differs at minor level | N.A.  |
| Resultant version decreases and differs at patch level | N.A.  |
| Resultant version unchanged                            | Minor |
| Resultant version increases and differs at patch level | Minor |
| Resultant version increases and differs at minor level | Minor |
| Resultant version increases and differs at major level | Major |

### Use a wildcard reference at major level

For most artefacts it is not advised to wildcard at the major level. An example of adding a wildcard reference at the minor level is setting the version to 1+.0.0.

| Action                                | Minimum Version Change |
|---------------------------------------|:----------------------:|
| Resultant version decreases and differs at major level | N.A.  |
| Resultant version decreases and differs at minor level | N.A.  |
| Resultant version decreases and differs at patch level | N.A.  |
| Resultant version unchanged                            | Major |
| Resultant version increases and differs at patch level | Major |
| Resultant version increases and differs at minor level | Major |
| Resultant version increases and differs at major level | Major |
