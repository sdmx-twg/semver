# ValueList

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Add a ValueItem | Minor | Datasets referencing the added ValueItem will not be valid for previous versions of the ValueList. |
| Remove a ValueItem | Major | Datasets referencing the removed ValueItem would no longer be valid. |
| Modify a ValueItem's ID | Major | This action corresponds to removing the original ValueItem then adding a ValueItem with the new id. |
| Add a Name to a ValueItem | Patch | |
| Remove a Name from a ValueItem | Patch | |
| Modify a ValueItem's Name | Patch | |
| Add a Description to a ValueItem | Patch | |
| Remove a Description from a ValueItem | Patch | |
| Modify a ValueItem's Description | Patch | |

## Wildcarding Considerations

A ValueLists does not reference other versionable artefacts.
