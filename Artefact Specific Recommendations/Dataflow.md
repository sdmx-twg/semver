# Dataflow

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Change the Structure reference | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |

## Wildcarding Considerations

Dataflows can reference other versionable artefacts in their structure references.

### Structure references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to the Structure. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to the Structure. Major changes to the structure can change the validity of the data. For example, this could result in required fields not being present. |
