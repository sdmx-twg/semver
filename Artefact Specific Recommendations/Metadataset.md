# Metadataset

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Change the Metadataflow reference | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| Change the MetadataProvisionAgreement reference | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| Switch between a Metadataflow reference and a MetadataProvisionAgreement reference | Major | Even if the definitions of the structure are identical, this changes to context of the metadataset and should be treated as a major change. |
| Add a Target | Patch | |
| Remove a Target | Patch | |
| Change a Target's value | Patch | |
| Modify Attribute(s) in any way | Patch | These are the values being reported. |
| Modify Action | Patch | |
| Modify reportingBeginDate | Patch | |
| Modify reportingEndDate | Patch | |
| Modify publicationYear | Patch | |
| Modify publicationPeriod | Patch | |

## Wildcarding Considerations

Metadatasets can reference other versionable artefacts in their references to a Metadataflow, a MetadataProvisionAgreement, and Target references.

### Metadataflow references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to the Metadataflow. |
| Major | 🟥 | It is not recommended to allow major wildcarding to a Metadataflow. The Metadataset could become invalid because of changes to the Structure of the referenced Metadataflow. |

### MetadataProvisionAgreement references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with concerns with having a minor wildcard reference to the MetadataProvisionAgreement. |
| Major | 🟥 | It is not recommended to allow major wildcarding as the Metadataset could become invalid because of changes to the Structure of the referenced MetadataProvisionAgreement. |

### Target references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference a target. |
| Major | 🟥 | It is not recommended to allow major wildcarding. The meaning of the Target could change with a major version change of that Target. |
