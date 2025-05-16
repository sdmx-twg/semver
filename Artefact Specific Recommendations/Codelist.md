# Codelist

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Add a Code | Minor | Hierarchies referencing the added code will not be valid for previous versions of the Codelist. |
| Remove a Code | Major | Hierarchies referencing the removed code would no longer be valid. |
| Modify a Code's ID | Major | This action corresponds to removing the original code then adding a code with the new id. Hierarchies referencing the code would no longer be valid as the reference includes the id of the code. |
| Add a Name to a Code | Patch | |
| Remove a Name from a Code | Patch | |
| Modify a Code's Name | Patch | |
| Add a Description to a Code | Patch | |
| Remove a Description from a Code | Patch | |
| Modify a Code's Description | Patch | |
| Add a CodelistExtension | Minor | Adding a meaningful CodelistExtension will add codes to the Codelist resulting in a minor change. |
| Remove a CodelistExtension | Major | Removing a meaningful CodelistExtension will remove codes from the Codelist resulting in a major change. |
| Modify a CodelistExtension's Codelist Reference | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Modify a CodelistExtension's prefix | Major | Changing the prefix removes all the codes with the old prefix and adds new codes with the new prefix. |
| Modify a CodelistExtension's inclusive/exclusive Code selection | Depends | If the set of codes extending the Codelist doesn't change then this would be a patch. If the original set of codes is a proper subset of the new set of codes extending the Codelist then this would be a minor change. If codes are removed from the set of codes extending the Codelist then this would be a major change. |

## Wildcarding Considerations

Codelists can reference other versionable artefacts with their CodelistExtension which references a Codelist from which to extend.

### Codelist references within CodelistExtension

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | With a minor wildcard new Codes would be added to the Codelist, this should only be allowed when the additions would not change the meaning of existing Codes. For example, a Code with the name "Other" could change it's meaning in a way which would not be obvious based on Code selection rules within the CodelistExtension. |  
| Major | 🟥 | It is not recommended to allow major wildcarding within the Codelist extension. If a code was removed from the CodelistExtension then a dependent metadataset could have data which is no longer valid. |
