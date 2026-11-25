# GeographicCodelist

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Add a GeoFeatureSetCode | Minor | Datasets referencing the added GeoFeatureSetCode will not be valid for previous versions of the GeographicCodelist. |
| Remove a GeoFeatureSetCode | Major | Datasets refering to the removed GeoFeatureSetCode would no longer be valid. |
| Modify a GeoFeatureSetCode's ID | Major | This action corresponds to removing the original GeoFeatureSetCode then adding a GeoFeatureSetCode with the new id. |
| Add a Name to a GeoFeatureSetCode | Patch | |
| Remove a Name from a GeoFeatureSetCode | Patch | |
| Change a GeoFeatureSetCode's Name | Patch | |
| Add a Description to a GeoFeatureSetCode | Patch | |
| Remove a Description from a GeoFeatureSetCode | Patch | |
| Change a GeoFeatureSetCode's Description | Patch | |
| Change a GeoFeatureSetCode's Value | Patch | |
| Add a validFrom to a GeoFeatureSetCode | Major | Adding a validFrom makes the validity period more restrictive. |
| Remove a validFrom from a GeoFeatureSetCode | Minor | Removing a validFrom makes the validity period less restrictive. |
| Modify a GeoFeatureSetCode's validFrom | Depends | If the validFrom date is moved forward in time, then the change is more restrictive and so this is a major change. If the date is moved backwards in time, then the change is less restrictive and so this is a minor change. If only the representation is changed, without changing the effective validity period, then this is a patch change. |
| Add a validTo to a GeoFeatureSetCode | Major | Adding a validTo makes the validity period more restrictive. |
| Remove a validTo from a GeoFeatureSetCode | Minor | Removing a validTo makes the validity period less restrictive. |
| Modify a GeoFeatureSetCode's validTo | Depends | If the validTo date is moved backwards in time, then the change is more restrictive and so this is a major change. If the  date is moved forward in time, then the change is less restrictive and so this is a minor change. If only the representation is changed, without changing the effective validity period, then this is a patch change. |
| Add a CodelistExtension | Minor | Adding a meaningful CodelistExtension will add GeoFeatureSetCodes to the GeographicCodelist resulting in a minor change. |
| Remove a CodelistExtension | Major | Removing a meaningful CodelistExtension will remove GeoFeatureSetCodes from the GeographicCodelist resulting in a major change. |
| Change a CodelistExtension's Codelist Reference | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| Change a CodelistExtension's prefix | Major | Changing the prefix removes all the GeoFeatureSetCodes with the old prefix and adds new GeoFeatureSetCodes with the new prefix. |
| Change a CodelistExtension's inclusive/exclusive Code selection | Depends | If the set of GeoFeatureSetCodes extending the GeographicCodelist doesn't change then this would be a patch. If the original set of GeoFeatureSetCodes is a proper subset of the new set of GeoFeatureSetCodes extending the GeographicCodelist then this would be a minor change. If GeoFeatureSetCodes are removed from the set of codes extending the GeographicCodelist then this would be a major change. |

## Wildcarding Considerations

GeographicCodelist can reference other versionable artefacts with their CodelistExtension which references a GeographicCodelist from which to extend.

### Codelist references within CodelistExtension

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | With a minor wildcard new GeoFeatureSetCodes would be added to the GeographicCodelist, this should only be allowed when the additions would not change the meaning of existing GeoFeatureSetCodes. |  
| Major | 🟥 | It is not recommended to allow major wildcarding within the CodelistExtension. A GeoFeatureSetCode mentioned in the Code selection rules within the CodelistExtension may no longer be part of the GeographicCodelist being referenced. |
