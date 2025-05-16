# ProvisionAgreement

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Modify Dataflow reference | Depends |  See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Modify DataProvider reference | Major | The only modifications allowed are to either change the agency of the DataProviderScheme or to change the data provider. Either of these changes fundamentally alters the ProvisionAgreement. |

## Wildcarding Considerations

ProvisionAgreements can reference other versionable artefacts with their Dataflow and DataProvider references.

### Dataflow references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to the Dataflow. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to the Dataflow. The structure of your Dataflow can change in a way which breaks existing data being provided under the ProvisionAgreement. |

### DataProvider references

The DataProviderScheme is fixed to version 1.0 so wildcarding cannot be applied to this reference.
