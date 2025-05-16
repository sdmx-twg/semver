# Categorisation

Categorisations work closely with [CategorySchemes](./CategoryScheme.md). In a categorisation the source is the artifact which is being categorised and the target is the CategoryScheme this categorisation is related to.

## Actions

In SDMX 3.1 a Categorization’s version is fixed to 1.0, so any action taken does not impact version number.

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
| Minor | ⚠️ | A minor wildcard reference will apply to all versions of the categorization matching that wildcarding. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a target as the targeted categorization may no longer exist in the CategoryScheme. |
