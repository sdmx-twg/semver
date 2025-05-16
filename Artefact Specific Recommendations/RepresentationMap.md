# RepresentationMap

Notes:

- source field references to the SourceCodelist and SourceDatatype elements.
- target field references to the TargetCodelist and TargetDatatype elements.

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|-------|:---------------:|---------|
| Adding a source field | Major | Adding a source results in a major change because it is changing the number of elements in the source mapping.  |
| Removing a source field | Major | Removing a source results in a major change because it is changing the number of elements in the source mapping. |
| Changing the order of the source fields | Major | Changing the order of sources results is a major change because it is changing the order of the source being mapped, potentialy breaking existing use of the RepresentationMap. |
| Changing a SourceCodelist being referenced | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Changing the type of a SourceDatatype | Major | This changes the valid use of the RepresentationMap. |
| Changing between SourceCodelist and SourceDatatype | Major | This changes the valid use of the RepresentationMap. |
| Adding a target field | Major | Adding a target results in a major change because it is changing the number of elements in the target mapping. |
| Removing a target field | Major |Adding a target results in a major change because it is changing the number of elements in the target mapping. |
| Changing the order of the target fields | Major | Changing the order of targets results in a major change because it is changing the order of the target being mapped, breaking existing use of the RepresentationMap.|
| Changing a TargetCodelist being referenced |Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Changing the type of a TargetDatatype | Major | This changes the valid use of the RepresentationMap |
| Changing between TargetCodelist and TargetDatatype | Major | This changes the valid use of the RepresentationMap. |
| Add a RepresentationMapping | Patch | |
| Remove a RepresentationMapping | Patch | |
| Add a SourceValue to a RepresentationMapping | Patch | |
| Remove a SourceValue to a RepresentationMapping | Patch | |
| Modify a RepresentationMapping's SourceValue | Patch | |
| Modify a RepresentationMapping's SourceValue's isRegEx | Patch | |
| Modify a RepresentationMapping's SourceValue's startIndex | Patch | |
| Modify a RepresentationMapping's SourceValue's endIndex | Patch | |
| Modify a RepresentationMapping's validFrom | Patch | |
| Modify a RepresentationMapping's validTo | Patch | |
| Add a TargetValue to a RepresentationMapping | Patch | |
| Remove a TargetValue to a RepresentationMapping | Patch | |
| Modify a RepresentationMapping TargetValue | Patch | |

## Wildcarding Considerations

Representation maps can reference other versionable artefacts in their SourceCodelist and TargetCodelist references.

### SourceCodelist references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | With a minor wildcard reference to a SourceCodelist newly added codes may be unmapped depending on the RepresentationMap's configuration. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the SourceCodelist. A RepresentationMapping may no longer valid as the SourceValue may have been removed from the SourceCodelist. |  

### TargetCodelist references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference in a TargetCodelist reference. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the TargetCodelist. A RepresentationMapping may no longer valid as the TargetValue may have been removed from the TargetCodelist. |
