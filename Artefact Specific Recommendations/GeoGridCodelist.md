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

## Wildcarding Considerations

GeoGridCodelist does not reference other versionable artefacts.
