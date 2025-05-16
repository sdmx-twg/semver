# ConceptScheme

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Add a Concept | Minor |  |
| Remove a Concept | Major | Artefacts referencing removed concept will no longer be valid. |
| Modify a Concept's id | Major | This action coorspondes to removing a concept with the old id then adding a concept with the new id. |
| Add a Name to a Code | Patch | |
| Remove a Name from a Code | Patch | |
| Modify a Concept's Name | Depends | If changing the Name results in changing the meaning of the concept then this would be a major change, otherwise this would be a patch. |
| Add a Description to a Concept | Patch | |
| Remove a Description from a Concept  | Patch | |
| Modify a Concept's  Description | Patch | |
| Modify a Concept's Modify CoreRepresentation from TextFormat to Enumeration | Major | Information which conformed to the text format could no longer be valid aginst the enumeration. |
| Modify Concept: Modify CoreRepresentation from Enumeration to TextFormat | Major | Enumerated values would continue to be valid as text but name and description information is lost to the end user. |
| Modify Concept: Modify CoreRepresentation change enumeration codelist reference | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| Modify Concept: Modify CoreRepresentation: Add EnumerationFormat | Major | Adding an EnumerationFormat could make values that were valid without an EnumerationFormat no longer valid. |
| Modify Concept: Modify CoreRepresentation: Remove EnumerationFormat | Minor | Removing the EnumerationFormat would make the enumeration less restrictive. |
| Modify Concept: Modify CoreRepresentation: Modify EnumerationFormat | Major | It is advised not to perform this action because core representations are to be used across data strucutres so this sort of fundamental modifications should be done sparingly. |
| Add a Parent to a Concept | Major | Any aggeration based on this parent relationship would break. |
| Remove a Parent from a Concept | Major | Any aggeration based on this parent relationship would break. |
| Change a Concept's  Parent | Major | Any aggeration based on this parent relationship would break. |
| Add ISOConceptReference to a concept | Minor | Refining the meaning of the concept. |
| Remove ISOConceptReference from a Concept | Major | Removing the ISOConceptReference is changing the meaning of the concept. |
| Modify a Concept's ISOConceptReference | Major | Changing the ISOConceptReference is changing the meaning of the concept. |

## Wildcarding Considerations

Conceptschemes can reference Codelists via the CoreRepresentations of their concepts.

### Codelists references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to codelists. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a codelist. An artefacts dependent on the Concept, such as a metadataset, could have data which is no longer valid. |
