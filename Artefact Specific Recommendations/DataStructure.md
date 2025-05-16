# DataStructure

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

A DataStructure is a complex object with many possible actions. The possible actions have been grouped to facilitate the usability of this guide.

* [Dimension-related actions](#dimension-related-actions)
* [Measure-related actions](#measure-related-actions)
* [Attribute-related actions](#attribute-related-actions)
* [MetadataAttribute-related actions](#metadataattribute-related-actions)
* [Group-related actions](#group-related-actions)

### Dimension-related actions

Including both Dimensions and TimeDimension

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Switch evolvingStructure from True to False | Minor | Existing Dataflows can continue to use the DataStructure, this is just a strengthening of versioning rules. A new Dataflow which is wildcarded to this version would not be backward compatible as it is not required to have a DimensionConstraint. |
| Switch evolvingStructure from False to True | Major | Setting evolvingStructure to true allows adding a dimension, which is otherwise a major change to be a minor change. To protect wildcarded Dataflows from this change in behaviour this must be a major change. |
| Add a Dimension or TimeDimension | Depends | If EvolvingStructure is set to True then this is a minor change. If EvolvingStructure is set to False then this is a major change. |
| Remove a Dimension or TimeDimension | Major | This would break existing queries to the dataflow using a key. |
| Change a Dimension's ID | Major | This refers to modifying the ID in the URN of the dimension. |
| Modify a Dimension's Position | Major | This would break existing queries to the dataflow using a key. |
| Modify Dimension or TimeDimension's ConceptIdentity | Depends | If changing the concept referenced within a ConceptScheme then this will be a major change as the meaning is changing. If changing the references to the ConceptScheme see [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| LocalRepresentation-related actions | Depends | See [LocalRepresentation-related actions](#localrepresentation-related-actions) for listing of actions and impacts. |
| ConceptRole-related actions | Depends | See [ConceptRole-related actions](#conceptrole-related-actions) for listing of actions and impacts. |

### Measure-related actions

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Add an optional Measure | Minor | Existing datasets would not be able to add data for this measure. |
| Add a mandatory Measure | Major | Existing datasets would not have data for this measure. |
| Remove a Measure | Major | This change would remove data from existing datasets. |
| Modify a Measure's UsageType from optional to mandatory | Major | Datasets based on the old version of the DataStructure may not have data for this measure.|
| Modify a Measure's UsageType from mandatory to optional | Minor | This change is not backward compatiable as a dataset based on the new DataStructure may no longer populate this measure. |
| Modify a Measure's ConceptIdentity | Depends |  If changing the concept referenced within a ConceptScheme then this will be a major change as the meaning is changing. If changing the references to the ConceptScheme see [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details.  [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| LocalRepresentation-related actions | Depends | See [LocalRepresentation-related actions](#localrepresentation-related-actions) for listing of actions and impacts. |
| ConceptRole-related actions | Depends | See [ConceptRole-related actions](#conceptrole-related-actions) for listing of actions and impacts. |

### Attribute-related actions

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Add an optional Attribute | Minor | Existing datasets would not be able to add metadata for this Attribute. |
| Add a mandatory Attribute | Major | Existing datasets would not have metadata for this Attribute. |
| Remove an Attribute | Major | This change would remove metadata from existing datasets. |
| Change an Attribute's ID | Major | This refers to modifying the ID in the URN of the Attribute. |
| Modify an Attribute's UsageType from optional to mandatory | Major | Datasets based on the old version of the DataStructure may not have metadata for this Attribute. |
| Modify an Attribute's UsageType from mandatory to optional | Minor | This change is not backward compatible as a dataset based on the new DataStructure may no longer populate this Attribute. |
| Modify an Attribute's AttributeRelationship | Major | This is the attachment level of the Attribute so existing information in this Attribute would no longer be valid. |
| Modify an Attribute's MeasureRelationship | Major | This would either be adding or removing measures which the Attribute is applicable for, which could change the meaning of the data. |
| Modify ConceptIdentity | Depends |  If changing the concept referenced within a ConceptScheme then this will be a major change as the meaning is changing. If changing the references to the ConceptScheme see [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details.  [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| LocalRepresentation-related actions | Depends | See [LocalRepresentation-related actions](#localrepresentation-related-actions) for listing of actions and impacts. |
| ConceptRole-related actions | Depends | See [ConceptRole-related actions](#conceptrole-related-actions) for listing of actions and impacts. |

### MetadataAttribute-related actions

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Add a MetdataStructrue reference | Patch | The action itself doesn't change that structure but subsequent use of MetadataAttributes will result in at least a Minor change. |
| Modify a MetdataStructrue reference | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Remove aMetdataStructrue reference where MetadataAttributes are used | Major | Any MetadataAttributes would also be removed when removing the MetadataStructure.  |
| Remove a MetdataStructrue reference where MetadataAttributes are not used | Patch | There is no impact to data or metadata in a dependent dataset.  |
| Add an optional MetadataAttribute | Minor | Existing datasets would not be able to add metadata for this MetadataAttribute. Note a MetadataAttribute being optional is defined in the related MetdataStructrue. |
| Add mandatory MetadataAttribute | Major | Existing datasets would not have metadata for this MetadataAttribute. Note a MetadataAttribute being mandatory is defined in the related MetdataStructrue. |
| RemoveMetadataAttribute | Major | This change would remove metadata from existing datasets. |
| Modify MetadataAttribute's MetadataAttributeReference | Major | This is effectively removing one MetadataAttribute and replacing it with another from the attached MetdataStructrue. |
| Modify MetadataAttribute's AttributeRelationship | Major | This is the attachment level of the MetadataAttribute so existing metadata in this MetadataAttribute would no longer be valid. |
| Modify ConceptIdentity | Depends |  If changing the concept referenced within a ConceptScheme then this will be a major change as the meaning is changing. If changing the references to the ConceptScheme see [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details.  [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| LocalRepresentation-related actions | Depends | See [LocalRepresentation-related actions](#localrepresentation-related-actions) for listing of actions and impacts. |

### Group-related actions

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Modify a Group’s id | Major | Any associated attributes and metadata attributes attachments would need to be updated to use the new id, which is a major change. |
| Modify a Group’s URN | N/A | The URN is formed the DataStructure’s URN and the Group’s id and should not change on its own. |
| Add a GroupDimension | Major | This changes the attachment level of any associated attributes and metadata attributes. |
| Remove a GroupDimension | Major | This changes the attachment level of any associated attributes and metadata attributes. |
| Modify a GroupDimension | Major | This changes the attachment level of any associated attributes and metadata attributes. |

### LocalRepresentation-related actions

Dimensions, TimeDimensions, Attributes, MetadataAttributes and Measures all can have LocalRepresentations, related Actions are grouped and described below:

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Add a LocalRepresentation | Major | While you are reusing the meaning of the concept you are fundamentally changing the Enumeration or TextFormat used to support it. |
| Remove a LocalRepresentation | Major | You are reverting to using the core representation of this concept, likely changing the supporting Enumeration or TestFormat. |
| Switch a LocalRepresentation from TextFormat to Enumeration | Major | Information which conformed to the TextFormat could no longer be valid against the enumeration. |
| Switch a LocalRepresentation from Enumeration to TextFormat | Major | Enumerated values would continue to be valid as text but name and description information is lost to the end user. |
| Modify a LocalRepresentation’s TextFormat | Major | This action changes the values which can be stored in the field. |
| Modify a LocalRepresentation’s Enumeration reference | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Add an EnumerationFormat to a LocalRepresentation | Major | Adding an EnumerationFormat could make values that were valid without an EnumerationFormat no longer valid. |
| Remove an EnumerationFormat from a LocalRepresentation | Minor | Removing the EnumerationFormat would make the enumeration less restrictive. |
| Modify a LocalRepresentation’s  EnumerationFormat | Major | It is advised not to perform this action because core representations are to be used across data structures so this sort of fundamental modifications should be done sparingly. |

### ConceptRole-related actions

Dimensions, Attributes, and Measures all have ConceptRoles. Note that [Guidelines for SDMX Concept Roles](https://sdmx.org/wp-content/uploads/Guidelines_for_SDMX_Concept_Roles_v1.0.docx) describes the use of ConceptRole in detail. These actions are grouped and described below:

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Add a ConceptRole | Minor | This action can change how the dataset will be processed or visualized by external tools. |
| Remove a ConceptRole | Minor | This action can change how the dataset will be processed or visualized by external tools. |
| Modify ConceptRole reference | Depends |  If changing the concept referenced within a ConceptScheme then this will be a major change as the meaning is changing. If changing the references to the ConceptScheme see [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details.  [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |

## Wildcarding Considerations

A DataStructure can reference other versionable artefacts in many places:

* MetdataStructrue reference
* ConceptSchemes references in ConceptIdentities
* Enumeration reference within a LocalRepresentation
* ConceptSchemes references in ConceptRoles

### MetdataStructrue reference

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference within the MetdataStructrue reference. |  
| Major | 🟥 | It is not recommended to allow major wildcarding within the MetdataStructrue reference. A MetadataAttribute being used by the DataStructure may have been removed from the MetdataStructrue making the DataStructure no longer valid. |

### ConceptSchemes references in ConceptIdentities

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a ConceptScheme refereced in a ConceptIdentity. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a referenced Concept within a ConceptScheme. The Concept being referenced may have been removed, making the ConceptIdentity no longer valid. |

### Codelists references in a LocalRepresentations' Enumerations

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a codelists within a LocalRepresentation's Enumeration. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a codelists within a LocalRepresentation's Enumeration. A Dataflow dependent on the DataStructure could have data associated with a code that was removed from the codelist makeing that data no longer valid. |

### ConceptSchemes references in ConceptRoles

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a ConceptScheme references in ConceptRoles. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a referenced Concept within a ConceptScheme. The Concept being referenced may have been removed, making the ConceptRole no longer valid. |
