# DataConsumerScheme

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments |
| ------ | :--------------------: | -------- |
| Add a DataConsumer | Minor | References to this DataConsumer will not be valid for previous versions of the DataConsumerScheme. |
| Remove a DataConsumer | Major | References to this DataConsumer will no longer be valid. |
| Add a Name to a DataConsumer | Patch | |
| Remove a Name from a DataConsumer | Patch | |
| Modify a DataConsumer's Name | Patch | |
| Add a Description to a DataConsumer | Patch | |
| Remove a Description from a DataConsumer | Patch | |
| Modify a DataConsumer's Description | Patch | |
| Add a Contact to a DataConsumer | Patch | |
| Remove a Contact from a DataConsumer | Patch | |
| Modify a DataConsumer's Contact | Patch | |
| Modify a DataConsumer's order within the DataConsumerScheme | Patch | |

## Wildcarding Considerations

A DataConsumerScheme does not reference other versionable artefacts.
