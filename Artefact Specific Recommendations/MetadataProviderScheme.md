# MetaMetadataProviderScheme

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments |
| ------ | :--------------------: | -------- |
| Add a MetadataProvider | Minor | References to this MetadataProvider will not be valid for previous versions of the MetadataProviderScheme. |
| Remove a MetadataProvider | Major | References to this MetadataProvider will no longer be valid. |
| Add a Name to a MetadataProvider | Patch | |
| Remove a Name from a MetadataProvider | Patch | |
| Modify a MetadataProvider's Name | Patch | |
| Add a Description to a MetadataProvider | Patch | |
| Remove a Description from a MetadataProvider | Patch | |
| Modify a MetadataProvider's Description | Patch | |
| Add a Contact to a MetadataProvider | Patch | |
| Remove a Contact from a MetadataProvider | Patch | |
| Modify a MetadataProvider's Contact | Patch | |
| Modify a MetadataProvider's order within the MetadataProviderScheme | Patch | |

## Wildcarding Considerations

A MetadataProviderScheme does not reference other versionable artefacts.
