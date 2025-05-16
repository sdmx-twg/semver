# Process

Note: The Computation in any ProcessStep is informational rather than machine actionable. In line with this we treat the entire process as informational and so most actions result in a patch.

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Add a ProcessStep | Minor | References to LocalIDs within the new process step would not be valid for previous versions of the Process. |
| Remove a ProcessStep | Major | References to LocalIDs within a Process step would break. |
| Modify a ProcessStep's placement in hierarchy to a different parent | Major | This would change the hierarical LocalID for the step, which would break existing references. |
| Modify a ProcessStep's placement in hierarchy within the same parent | Patch |  |
| Add an Input to a ProcessStep | Patch | |
| Remove an Input from a ProcessStep | Patch | |
| Modify an Input's ObjectReference | Patch | |
| Modify an Input's LocalID | Major | References to the existing LocalID would break. |
| Add an Output to a ProcessStep | Patch | |
| Remove an Output from a ProcessStep | Patch | |
| Modify an Output's ObjectReference | Patch | |
| Modify an Output's LocalID | Major | References to the existing LocalID would break. |
| Add a Computation to a ProcessStep | Patch | |
| Remove a Computation from a ProcessStep | Patch | |
| Modify add a Computation's Description | Patch | |
| Modify remove a Computation's Description | Patch | |
| Modify a Computation's Description| Patch | |
| Modify a Computation's LocalID | Major | References to the existing LocalID would break. |
| Modify a Computation's softwarePackage | Patch | |
| Modify a Computation's softwareLanguage | Patch | |
| Modify a Computation's softwareVersion | Patch | |
| Add a Transition to a ProcessStep | Patch | |
| Remove a Transition from a ProcessStep | Patch | |
| Modify a Transition's TargetStep | Patch | |
| Add a Transition's Condition | Patch | |
| Remove a Transition's Condition | Patch | |
| Modify a Transition's Condition | Patch | |
| Modify a Transition's LocalID | Major | References to the existing LocalID would break. |

## Wildcarding Considerations

A Process can reference other versionable artefacts through their ProcessStep's Input and Output ObjectReference.

### Input ObjectReference within a ProcessStep

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference within an Input ObjectReference. |
| Major | 🟢 | There are no concerns with having a major wildcard reference within an Input ObjectReference. |

### Output ObjectReference within a ProcessStep

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference within an Output ObjectReference. |
| Major | 🟢 | There are no concerns with having a major wildcard reference within an Output ObjectReference. |
