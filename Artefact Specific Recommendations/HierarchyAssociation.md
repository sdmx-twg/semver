# HierarchyAssociation

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Modify LinkedHierarchy | Patch | |
| Modify LinkedObject | Patch | |
| Add ContextObject | Patch | |
| Remove ContextObject | Patch | |
| Modify ContextObject | Patch | |

## Wildcarding Considerations

HierarchyAssociation can reference other versionable artefacts in their LinkedHierarchy, LinkedObject, and ContextObject references.

### LinkedHierarchy references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a LinkedHierarchy. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a LinkedHierarchy. The LinkedHierarchy may no longer be applicable following a major change to the LinkedHierarchy. |

### LinkedObject references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a LinkedObject references. |  
| Major | 🟥 | It is not recommended to allow major wildcarding to a LinkedObject. The LinkedHierarchy may no longer be applicable following a major change to the LinkedObject. |

### ContextObject references

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference to a ContextObject references. |  
| Major | 🟢 | There are no concerns with having a minor wildcard reference to a ContextObject references. |
