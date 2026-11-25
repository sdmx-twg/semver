# OrganisationSchemeMap

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Modify Source | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| Modify Target | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
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

OrganisationSchemeMap can reference other versionable artefacts in their Source and Target OrganisationScheme references. OrganisationScheme references are either AgencyScheme, DataConsumerScheme, DataProviderSceheme, or OrganisationUnitScheme references. Note  AgencySchemes are fixed to version 1.0 so wildcarding is not possible, the below guidance references to the other types of references..

### Source OrganisationScheme references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | With a minor wildcard reference to a Source OrganisationScheme newly added Organizations may be unmapped depending on the OrganisationSchemeMap's configuration. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the Source OrganisationScheme. An OrganisationSchemeMap may no longer valid as the Source Organisation may have been removed from the Source OrganisationScheme. |  

### Target OrganisationScheme references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference in a Target OrganisationScheme references. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the Target OrganisationScheme. A OrganisationSchemeMap may no longer valid as the Target Organisation may have been removed from the Target OrganisationScheme. |

