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
| Add a validFrom to a ValueItem | Major | Adding a validFrom makes the validity period more restrictive. |
| Remove a validFrom from a ValueItem | Minor | Removing a validFrom makes the validity period less restrictive. |
| Modify a ValueItem's validFrom | Depends | If the validFrom date is moved forward in time, then the change is more restrictive and so this is a major change. If the date is moved backwards in time, then the change is less restrictive and so this is a minor change. |
| Add a validTo to a ValueItem | Major | Adding a validTo makes the validity period more restrictive. |
| Remove a validTo from a ValueItem | Minor | Removing a validTo makes the validity period less restrictive. |
| Modify a ValueItem's validTo | Depends | If the validTo date is moved backwards in time, then the change is more restrictive and so this is a major change. If the  date is moved forward in time, then the change is less restrictive and so this is a minor change. |

## Wildcarding Considerations

A ValueLists does not reference other versionable artefacts.
