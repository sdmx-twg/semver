# CategoryScheme

CategorySchemes work closely with [Categorisations](./Categorisation.md).

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Add a Category | Minor | Categorisations referencing the added category will not be valid for previous versions of the CategoryScheme. |
| Remove a Category | Major | Categorisations referencing the removed category would no longer be valid. |
| Modify a Category's id | Major | This action corresponds to removing the original category then adding a category with the new id. Categorisations referencing the category would no longer be valid as the reference includes the id of the category. |
| Add a Name to a Category | Patch |  |
| Remove a Name from a Category| Patch |  |
| Modify a Category's Name | Patch |  |
| Add a Description to a Category | Patch |  |
| Remove a Description from a Category| Patch |  |
| Modify a Category's Description | Patch |  |
| Add a Link to a Category | Patch |  |
| Remove a Link from a Category| Patch |  |
| Modify a Link's Description | Patch |  |
| Modify a Category's Placement in hierarchy to a different parent | Major | Changing the parent of the category can change the meaning of the category. |
| Modify a Category's Placement in hierarchy with the same parent | Patch | Changing the order of children of a category does not impact the meaning of the category. |

## Wildcarding Considerations

A CategoryScheme does not reference other versionable artifacts.
