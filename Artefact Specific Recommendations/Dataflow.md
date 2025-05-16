# Dataflow

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Change the Structure reference | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| Add a DimensionConstraint | Depends | This should be a major change if the Dimensions listed in the DimensionConstraint is a proper subset of the Dimensions of the Structure. If the Dimensions listed in the DimensionConstraint equals the Dimensions of the Structure, then this is a patch. |
| Remove a DimensionConstraint | Depends | This should be a major change if the Dimensions listed in the DimensionConstraint is a proper subset of the Dimensions of the Structure. If the Dimensions listed in the DimensionConstraint equals the Dimensions of the Structure, then this is a patch. |
| Add a Dimension to a DimensionConstraint | Major | The dimensionality of the Dataflow is changing, which changes the validity of the data associated with the Dataflow. |
| Remove a Dimension from a DimensionConstraint | Major | The dimensionality of the Dataflow is changing, which changes the validity of the data associated with the Dataflow. |

## Wildcarding Considerations

Dataflows can reference other versionable artefacts in their structure references.

### Structure references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | If the Structure being referenced has evolvingStructure set to True, then a DimensionConstraint is required. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to the Structure. Major changes to the structure can change the validity of the data. For example, this could result in required fields not being present. |
