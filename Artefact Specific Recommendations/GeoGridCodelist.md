# GeoGridCodelist

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Modify the GridDefinition | Patch | |
| Add a GeoGridCode | Minor | Datasets referencing the added GeoGridCode will not be valid for previous versions of the GeoGridCodelist. |
| Remove a GeoGridCode | Major | Datasets refering to the removed GeoGridCode would no longer be valid. |
| Modify a GeoGridCode's ID | Major | This action corresponds to removing the original GeoGridCode then adding a GeoGridCode with the new id. |
| Add a Name to a GeoGridCode | Patch | |
| Remove a Name from a GeoGridCode | Patch | |
| Change a GeoGridCode's Name | Patch | |
| Add a Description to a GeoGridCode | Patch | |
| Remove a Description from a GeoGridCode | Patch | |
| Change a GeoGridCode's Description | Patch | |
| Change a GeoGridCode's GeoCell | Patch | |
| Add a validFrom to a GeoGridCode | Major | Adding a validFrom makes the validity period more restrictive. |
| Remove a validFrom from a GeoGridCode | Minor | Removing a validFrom makes the validity period less restrictive. |
| Modify a GeoGridCode's validFrom | Depends | If the validFrom date is moved forward in time, then the change is more restrictive and so this is a major change. If the date is moved backwards in time, then the change is less restrictive and so this is a minor change. |
| Add a validTo to a GeoGridCode | Major | Adding a validTo makes the validity period more restrictive. |
| Remove a validTo from a GeoGridCode | Minor | Removing a validTo makes the validity period less restrictive. |
| Modify a GeoGridCode's validTo | Depends | If the validTo date is moved backwards in time, then the change is more restrictive and so this is a major change. If the  date is moved forward in time, then the change is less restrictive and so this is a minor change. |

## Wildcarding Considerations

GeoGridCodelist does not reference other versionable artefacts.
