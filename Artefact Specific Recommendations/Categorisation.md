# Categorisation

Categorisations work closely with [CategorySchemes](./CategoryScheme.md). In a categorisation the source is the artifact which is being categorised and the target is the CategoryScheme this categorisation is related to.

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
|Change Source| Patch | |
|Change Target| Patch | |

## Wildcarding Considerations

Categorisations can reference other versionable artefacts in their Source and Target references.

### Source references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a source artefact. |  
| Major | ⚠️ | If the source artefact is not a maintainable artefact, then it is not recommended to allow major wildcarding as the source artefact may no longer exist (e.g. a code may be deleted from a codelist). If the source artefact is a maintainable artefact, then there are no concerns with having a major wildcard reference as this will allow the categorisation to always reference the latest version of the artefact. |  

### Target references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | A minor wildcard reference will apply to all versions of the Categorisation matching that wildcarding. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a target as the targeted Categorisation may no longer exist in the CategoryScheme.  |
