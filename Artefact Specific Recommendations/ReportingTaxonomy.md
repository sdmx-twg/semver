# ReportingTaxonomy

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Add a ReportingCategory | Minor | References to this ReportingCategory will not be valid for previous versions of the ReportingTaxonomy. |
| Remove a ReportingCategory | Major | References to this ReportingCategory will no longer be valid. |
| Add a Name to a ReportingCategory | Patch |  |
| Remove a Name from a ReportingCategory | Patch |  |
| Modify a ReportingCategory's Name | Patch |  |
| Add a Description to a ReportingCategory | Patch |  |
| Remove a Description from a ReportingCategory | Patch |  |
| Modify a ReportingCategory's Description | Patch |  |
| Modify a ReportingCategory's placement in the hierarchy to a different parent | Major | The meaning of the ReportingCategoty could change based on its parent. |
| Modify a ReportingCategory's placement in the hierarchy within the same parent | Patch |  |
| Switch a ReportingCategory between StructuralMetadata and ProvisioningMetadata | Major | The type of artefact which can be associated to this category is being changed. |
| Add a StructuralMetadata reference for a ReportingCategory | Minor | Modifying the content for a ReportingCategory is an important change for a user of the ReportingTaxonomy and needs to be flagged as greater than a patch. It is not a major change as this content cannot be directly referenced by a URN. |
| Remove a StructuralMetadata reference for a ReportingCategory | Minor | Modifying the content for a ReportingCategory is an important change for a user of the ReportingTaxonomy and needs to be flagged as greater than a patch. It is not a major change as this content cannot be directly referenced by a URN. |
| Modify a StructuralMetadata reference for a ReportingCategory | Depends | If the recommendations in [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) result in a Patch, treat the action as a patch otherwise treat it as a minor change as any modification can be accomplished by removing then adding a StructuralMetadata reference, which would result in a minor change. |
| Add a ProvisioningMetadata reference for a ReportingCategory | Minor | Modifying the content for a ReportingCategory is an important change for a user of the ReportingTaxonomy and needs to be flagged as greater than a patch. It is not a major change as this content cannot be directly referenced by a URN. |
| Remove a ProvisioningMetadata reference for a ReportingCategory | Minor | Modifying the content for a ReportingCategory is an important change for a user of the ReportingTaxonomy and needs to be flagged as greater than a patch. It is not a major change as this content cannot be directly referenced by a URN. |
| Modify a ProvisioningMetadata reference for a ReportingCategory | Depends | If the recommendations in [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) result in a Patch, treat the action as a patch otherwise treat it as a minor change as any modification can be accomplished by removing then adding a ProvisioningMetadata reference, which would result in a minor change. |

## Wildcarding Considerations

ReportingTaxonomies can reference other versionable artefacts throught their ReportingCategories' StructuralMetadata and ProvisioningMetadata.

### ReportingCategory structure references within StructuralMetadata

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference within the structure references. |  
| Major | 🟢 | There are no concerns with having a major wildcard reference within the structure references. |  

### ReportingCategory dataflow and metadaflow references within ProvisioningMetadata

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference within the dataflow or metadaflow references. |  
| Major | 🟢 | There are no concerns with having a major wildcard reference within the dataflow or metadaflow references. |
