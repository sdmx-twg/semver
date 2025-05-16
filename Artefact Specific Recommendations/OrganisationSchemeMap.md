# OrganisationSchemeMap

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Modify Source | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Modify Target | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Add ItemMap | Patch | |
| Remove ItemMap | Patch| |
| Modify ItemMap SourceValue | Patch | |
| Modify ItemMap SourceValue isRegEx | Patch | |
| Modify ItemMap SourceValue startIndex | Patch | |
| Modify ItemMap SourceValue endIndex | Patch | |
| Modify ItemMap TargetValue | Patch | |
| Modify ItemMap validFrom | Patch | |
| Modify ItemMap validTo | Patch | |

## Wildcarding Considerations

OrganisationSchemeMap can reference other versionable artefacts in their Source and Target OrganisationScheme references. OrganisationScheme references are either AgencyScheme, DataConsumerScheme, DataProviderSceheme, or OrganisationUnitScheme references. These other artefacts are all fixed to version 1.0 so wildcarding is not possible.
