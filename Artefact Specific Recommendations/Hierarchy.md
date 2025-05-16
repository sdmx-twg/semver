# Hierarchy

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Add a HierarchicalCode | Minor | |
| Remove a HierarchicalCode | Major | Client applications may be using this hierarcy in ways you don't expect such as an aggergation. In this case the removal could break things. |
| Change a HierarchicalCode's reference | Major | This action is the same as removing a HierarchicalCode then adding a new HierarchicalCode. |
| Add a Level | Minor | |
| Remove a Level | Major | Client applications may be using this hierarcy in ways you don't expect such as an aggergation |
| Change a Level's id | Major | This action corresponds to removing the original Level then adding a Level with the new id. |
| Add a Name to a Level | Patch | |
| Remove a Name from a Level | Patch | |
| Modify a Level's Name | Patch | |
| Add a Description to a Level | Patch | |
| Remove a Description from a Level | Patch | |
| Modify a Level's Description | Patch | |
| Add a CodingFormat to a Level | Patch | |
| Change CodingFormat of a Level | Patch | |
| Remove CodingFormat from a Level | Patch | |
| Change the hasFormalLevels attribute | Patch | This action does not dictate the existence of Levels but is just an indicator of Formal Levels. |

## Wildcarding Considerations

Hierarchies can reference other versionable artefacts as part of their references to HierarchicalCodes where they refer to the parent Codelist. **Note:** References are per HierarchicalCode so you could have codes pulling from the same parent Codelist being referenced in different ways.

### Codelist references within HierarchicalCodes

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | The hierarchy may become incomplete with respect to the supporting Codelist(s). |  
| Major | 🟥 | It is not recommended to allow major wildcarding of Codelists within HierarchicalCodes. The referenced code may no longer exist in the supporting Codelist(s). |
