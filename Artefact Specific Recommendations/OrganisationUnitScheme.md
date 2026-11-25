# OrganisationUnitScheme

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments |
| ------ | :--------------------: | -------- |
| Add a OrganisationUnit | Minor | References to this OrganisationUnit will not be valid for previous versions of the OrganisationUnitScheme. |
| Remove a OrganisationUnit | Major | References to this OrganisationUnit will no longer be valid. |
| Add a Name to a OrganisationUnit | Patch | |
| Remove a Name from a OrganisationUnit | Patch | |
| Modify a OrganisationUnit's Name | Patch | |
| Add a Description to a OrganisationUnit | Patch | |
| Remove a Description from a OrganisationUnit | Patch | |
| Modify a OrganisationUnit's Description | Patch | |
| Add a Contact to a OrganisationUnit | Patch | |
| Remove a Contact from a OrganisationUnit | Patch | |
| Modify a OrganisationUnit's Contact | Patch | |
| Modify a OrganisationUnit's placement in the hierarchy to a different parent | Patch | |
| Modify a OrganisationUnit's placement in the hierarchy within the same parent | Patch | |

## Wildcarding Considerations

A OrganisationUnitScheme does not reference other versionable artefacts.
