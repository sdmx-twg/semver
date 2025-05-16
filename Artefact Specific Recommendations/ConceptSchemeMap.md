# ConceptSchemeMap

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

ConceptSchemeMaps can reference other versionable artefacts in their Source and Target ConceptScheme references.

### Source ConceptScheme reference

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | With a minor wildcard reference new Concepts added to the Source ConceptScheme could be unmapped depending on the ConceptSchemeMap's configuration. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the Source ConceptScheme. An ItemMap may no longer be valid if its SourceValue was removed from the Source ConceptScheme. |  

### Target ConceptScheme reference

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a Target ConceptScheme. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the Target ConceptScheme. An ItemMap may no longer be valid if its TargetValue was removed from the Target ConceptScheme. |
