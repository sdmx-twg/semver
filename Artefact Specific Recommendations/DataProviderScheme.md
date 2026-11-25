# DataProviderScheme

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments |
| ------ | :--------------------: | -------- |
| Add a DataProvider | Minor | References to this DataProvider will not be valid for previous versions of the DataProviderScheme. |
| Remove a DataProvider | Major | References to this DataProvider will no longer be valid. |
| Add a Name to a DataProvider | Patch | |
| Remove a Name from a DataProvider | Patch | |
| Modify a DataProvider's Name | Patch | |
| Add a Description to a DataProvider | Patch | |
| Remove a Description from a DataProvider | Patch | |
| Modify a DataProvider's Description | Patch | |
| Add a Contact to a DataProvider | Patch | |
| Remove a Contact from a DataProvider | Patch | |
| Modify a DataProvider's Contact | Patch | |
| Modify a DataProvider's order within the DataProviderScheme | Patch | |

## Wildcarding Considerations

A DataProviderScheme does not reference other versionable artefacts.
