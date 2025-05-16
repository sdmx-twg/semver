# CategorySchemeMap

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Modify Source | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Modify Target | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Add an ItemMap | Patch | |
| Remove an ItemMap | Patch| |
| Modify an ItemMap's SourceValue | Patch | |
| Modify an ItemMap's SourceValue isRegEx | Patch | |
| Modify an ItemMap's SourceValue startIndex | Patch | |
| Modify an ItemMap's SourceValue endIndex | Patch | |
| Modify an ItemMap's TargetValue | Patch | |
| Modify an ItemMap's validFrom | Patch | |
| Modify an ItemMap's validTo | Patch | |

## Wildcarding Considerations

CategorySchemeMaps can reference other versionable artefacts in their Source and Target CategoryScheme references.

### Source CategoryScheme reference

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | With a minor wildcard reference new Categories added to the Source CategoryScheme could be unmapped depending on the CategorySchemeMap's configuration. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the Source CategoryScheme. An ItemMap may no longer be valid if its SourceValue was removed from the Source CategoryScheme. |  

### Target CategoryScheme reference

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a Target CategoryScheme. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the Target CategoryScheme. An ItemMap may no longer be valid if its TargetValue was removed from the Target CategoryScheme. |
