# MetadataStructure

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Add a MetadataAttribute with minOccurs = 0 | Minor | This MetadataAttribute is optional so existing Metadatasets will not break. |
| Add a MetadataAttribute with minOccurs <> 0 | Major | This MetadataAttribute is required so existing Metadatasets would break. |
| Remove a MetadataAttribute | Major | This MetadataAttribute may exist in a Metadataset, breaking that Metadataset. |
| Modify a MetadataAttribute's isPresentational attribute | Major | This is fundamentally changing the role of the MetadataAttribute. |
| Increase a MetadataAttribute's minOccures | Major | This is setting a stricter requirement on the number of occurrences of this MetadataAttribute potentially breaking existing Metadatasets. |
| Decrease a MetadataAttribute's minOccures | Minor | This is loosening the requirements on the number of occurrences of this MetadataAttribute. |
| Increase a MetadataAttribute's maxOccures | Minor | Metadatasets using the new higher maxOccures would not be backwards compatible. |
| Decrease a MetadataAttribute's maxOccures | Major | Any existing Metadataset using a high number of occurrences than the new maxOccures would break. |
| Modify a MetadataAttribute's ConceptIdentity | Depends | If changing the concept within a conceptScheme then this will be a major change as the meaning of the MetadataAttribute is changing. If changing the references to the ConceptScheme, see [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Switch a MetadataAttribute's LocalRepresentation from TextFormat to Enumeration | Major | Information which conformed to the text format could no longer be valid against the enumeration. |
| Switch a MetadataAttribute's LocalRepresentation from Enumeration to TextFormat | Major | Enumerated values would continue to be valid as text, but name and description information is lost to the end user. |
| Modify the TextFormat of a a MetadataAttribute's LocalRepresentation | Major | This changes the allowed values of the MetadataAttribute, potentially breaking existing Metadatasets. |
| Modify a MetadataAttribute's LocalRepresentation change Enumeration's Codelist reference | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Add an EnumerationFromat to a MetadataAttribute | Major | Adding an EnumerationFormat could make values that were valid without an EnumerationFormat no longer valid. |
| Remove an EnumerationFromat from a MetadataAttribute | Minor | Removing the EnumerationFormat would make the enumeration less restrictive. |
| Modify an EnumerationFromat of a MetadataAttribute | Minor | It is advised not to perform this action because core representations are to be used across data structures so this sort of fundamental modifications should be done sparingly. |
| Modify the hierarchy of MetadataAttributes | Major | The meaning of a given MetadataAttribute could change off a change in position within the hierarchy. |

## Wildcarding Considerations

MetadataStructure can reference ConcepySchemes vis their metadataAttributes' ConceptIdentity as well as Codelists via Enumeration references within their LocalRepresentations.

### ConceptSchemes references in ConceptIdentities

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a ConceptScheme. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a referenced Concept within a ConcepyScheme. The Concept may have been removed making the ConceptIdentity no longer valid. |

### Codelists references in Enumerations

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to Codelists within an Enumeration. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to an Enumeration. Artefacts dependent on the MetadataStructure, such as a metadataset, could have data associated with them which is no longer valid. |
