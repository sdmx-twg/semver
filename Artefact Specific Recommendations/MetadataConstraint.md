# MetadataConstraint

**Note:** The SDMX 3.1 Technical Specifications state:
>"When Data and Metadata Constraints are versioned, the latest version of the Constraint is used to generate the reporting restriction rules; all previous versions are for historical information only."

That same logic should be applied to SDMX 3.0 and is the basis for the recommendations below.

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Add an artefact to a ConstraintAttachment | Patch | |
| Remove an artefact from a ConstraintAttachment | Patch | |
| Add a ReleaseCalendar | Major | Adding a ReleaseCalendar results in a more restrictive constraint. |
| Remove a ReleaseCalendar | Minor | Removing a ReleaseCalendar results in a less restrictive constraint. |
| Modify a ReleaseCalendar's Periodicity | Depends | See [Note](Note) |
| Modify a ReleaseCalendar's Offset | Depends | See [Note](Note) |
| Modify a ReleaseCalendar's Tolerance | Depends | See [Note](Note) |
| Add a MetadataTagetRegion | Depends | See [Note](Note) |
| Remove a MetadataTargetRegion | Depends | See [Note](Note) |
| Modify a MetadataTargetRegion's include attribute | Depends | See [Note](Note) |
| Modify a MetadataTargetRegion's validFrom | Depends | See [Note](Note) |
| Modify a MetadataTargetRegion's validTo | Depends | See [Note](Note) |
| Add a Component to a MetadataTargetRegion | Depends | See [Note](Note) |
| Remove a Component from a MetadataTargetRegion | Depends | See [Note](Note) |
| Modify a Component's id | Depends | See [Note](Note) |
| Modify a Component's include attribute | Depends | See [Note](Note) |
| Modify a Component's removePrefix attribute | Depends | See [Note](Note) |
| Modify a Component's Value's cascadeValues attribute | Depends | See [Note](Note) |
| Modify a Component's Value's xml:lang attribute | Depends | See [Note](Note) |
| Modify a Component's Value's validFrom | Depends | See [Note](Note) |
| Modify a Component's Value's validTo | Depends | See [Note](Note) |
| Modify a Component's TimeRange's BeforePeriod | Depends | See [Note](Note) |
| Modify a Component's TimeRange's AfterPeriod | Depends | See [Note](Note) |
| Modify a Component's TimeRange's StartPeriod | Depends | See [Note](Note) |
| Modify a Component's TimeRange's EndPeriod | Depends | See [Note](Note) |
| Modify a Component's TimeRange's validFrom | Depends | See [Note](Note) |
| Modify a Component's TimeRange's validTo | Depends | See [Note](Note) |
| Switch a Component's TimeRange from using BeforePeriod or AfterPeriod to StartPeriod and EndPeriod | Depends | See [Note](Note) |
| Switch a Component's TimeRange from using StartPeriod and EndPeriod to BeforePeriod or AfterPeriod | Depends | See [Note](Note) |
| Switch Component's TimeRange from using BeforePeriod to AfterPeriod | Depends | See [Note](Note) |
| Switch a Component's TimeRange from using AfterPeriod to BeforePeriod | Depends | See [Note](Note) |
| Switch a Component from using TimeRange to Value | Depends | See [Note](Note) |
| Switch a Component from using Value to TimeRange | Depends | See [Note](Note) |

### Note

If the action results in a more restrictive constraint, then it should be a major change. If the action results in a less restrictive constraint, then it should be a minor change. If the action does not impact the restrictiveness of the constraint, i.e. it is simply a reformulation of the constraint, then it should be a patch.

## Wildcarding Considerations

A MetadataConstraint can reference other versionable artefacts in their ConstraintAttachment references.
The following are the versionable artefacts which can occur in a ConstraintAttachment:  

* MetadataProvider
* MetadataSet
* MetadataStructure
* Metadataflow
* MetadataProvisionAgreement

### Referenced artefact within ConstraintAttachment

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | If minor wildcarding is used then care should be taken to ensure that the MetadataConstraint is designed in such a way that there is no concern when new fields are added to the supporting referenced artefact. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the referenced artefact within ConstraintAttachment. The definition of the constraint may contain elements which are no longer part of the referenced artefact. For example, a MetadataAttribute could have been removed from a MetadataStructure. |
