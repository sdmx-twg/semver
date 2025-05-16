# MetadataProvisionAgreement

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Modify the Metadataflow reference | Depends |  See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Modify the MetadataProvider reference | Major | The only modifications allowed are to either change the agency of the MetadataProviderScheme or change the metadata provider. Either of these changes fundamentally alters the MetadataProvisionAgreement. |
| Add a Target | Patch | |
| Remove a Taget | Patch | |
| Modify a Target | Patch | |

## Wildcarding Considerations

MetadataProvisionAgreement can reference other versionable artefacts with their Metadataflow and MetadataProvider references as well as their Targets.

### Metadataflow references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to the Metadataflow. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to the Metadataflow. The structure of your Metadataflow can change in a way which breaks existing metadata being provided under the MetadataProvisionAgreement. |

### MetadataProvider references

The MetadataProviderScheme is fixed to version 1.0 so wildcarding cannot be applied to this reference.

### Target references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a Target. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a Target. The meaning of the Target could change with a major version change of that Target. |
