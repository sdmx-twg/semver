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
| Remove a Description from a GeoGridCode  | Patch | |
| Change a GeoGridCode's Description | Patch | |
| Change a GeoGridCode's GeoCell | Patch | |
| Add a CodelistExtension | Minor | Adding a meaningful CodelistExtension will add GeoGridCodes to the GeoGridCodelist resulting in a minor change. |
| Remove a CodelistExtension | Major | Removing a meaningful CodelistExtension will remove GeoGridCodes from the GeoGridCodelist resulting in a major change. |
| Change a CodelistExtension's Codelist Reference | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| Change a CodelistExtension's prefix | Major | Changing the prefix removes all the GeoGridCodes with the old prefix and adds new GeoGridCodes with the new prefix. |
| Change a CodelistExtension's inclusive/exclusive Code selection | Depends | If the set of GeoGridCodes extending the GeoGridCodelist doesn't change then this would be a patch. If the original set of GeoGridCodes is a proper subset of the new set of GeoGridCodes extending the GeoGridCodelist then this would be a minor change. If GeoGridCodes are removed from the set of codes extending the GeoGridCodelist then this would be a major change. |

## Wildcarding Considerations

GeoGridCodelist can reference other versionable artefacts with their CodelistExtension which references a GeoGridCodelist from which to extend.

### Codelist references within CodelistExtension

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | With a minor wildcard new GeoGridCodes would be added to the GeographicCodelist, this should only be allowed when the additions would not change the meaning of existing GeoGridCodes. |
| Major | 🟥 | It is not recommended to allow major wildcarding within the CodelistExtension. A GeoGridCodes mentioned in the Code selection rules within the CodelistExtension may no longer be part of the GeoGridCodelist being referenced. |
