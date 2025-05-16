# Metadataflow

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Change the Structure reference | Depends | See [Changing an artefact reference](../General%20Recommendations/Changing%20an%20artefact%20reference.md#changing-an-artefact-reference) for details. |
| Add a Target | Patch | |
| Remove a Target | Depends | If the set of all allowed targets doesn't change then this would be a patch. If this action results in the removal of an item from the set of possible targets, then the change would be a major change. |
| Change a Target's value | Depends | If none of the previously allowed targets is removed from the new set of targets this would be a patch. If this action results in the removal of an item from the set of possible targets, then the change would be a major change. |

## Wildcarding Considerations

Metadataflows can reference other versionable artefacts in their structure references as well as their Target references.

### Structure references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to the Structure. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to the Structure. Major changes to the structure can change the validity of the metadata. For example, this could result in required fields not being present. |

### Target references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a target.|  
| Major | ⚠️ | If the artefact being referenced is not a maintainable artefact, then major wildcarding should **not** be allowed as the artefact may no longer exist (e.g. a code within a codelist). If the artefact being referenced is a maintainable artefact, then major wildcarding should be allowed as this will allow the categorisation to always reference the latest version of the artefact. |
