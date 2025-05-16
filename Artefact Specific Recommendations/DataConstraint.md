# DataConstraint

**Note:** The SDMX Technical Specifications state:
>"When Data and Metadata Constraints are versioned, the latest version of the Constraint is used to generate the reporting restriction rules; all previous versions are for historical information only."

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Add an artefact to a ConstraintAttachment | Patch | |
| Remove an artefact from a ConstraintAttachment | Patch | |
| Add DataKeySet | Depends | See [Note](#note) |
| Remove DataKeySet | Depends | See [Note](#note) |
| Modify DataKeySet's isIncluded attribute | Depends | See [Note](#note) |
| Add a Key to DataKeySet | Depends | See [Note](#note) |
| Remove a Key from DataKeySet | Depends | See [Note](#note) |
| Add a Component to a DataKeyset's Key | Depends | See [Note](#note) |
| Remove a Component from a DataKeyset's Key | Depends | See [Note](#note) |
| Modify Modify DataKeyset's Key's Component's id | Depends | See [Note](#note) |
| Modify Modify DataKeyset's Key's Component's include attribute | Depends | See [Note](#note) |
| Modify Modify DataKeyset's Key's Component's removePrefix attribute | Depends | See [Note](#note) |
| Modify Modify DataKeyset's Key's Component's Value's cascadeValues attribute | Depends | See [Note](#note) |
| Modify Modify DataKeyset's Key's Component's Value's xml:lang attribute | Depends | See [Note](#note) |
| Modify Modify DataKeyset's Key's Component's TimeRange | Depends | See [TimeRange Related Actions](#timerange-related-actions) |
| Switch Modify DataKeyset's Key's Component from using TimeRange to Value | Depends | See [Note](#note) |
| Switch Modify DataKeyset's Key's Component from using Value to TimeRange | Depends | See [Note](#note) |
| Add a Keyvalue to a DataKeyset's Key | Depends | See [Note](#note) |
| Remove a Keyvalue from a DataKeyset's Key | Depends | See [Note](#note) |
| Modify DataKeyset's Key's Keyvalue's id | Depends | See [Note](#note) |
| Modify DataKeyset's Key's Keyvalue's value | Depends | See [Note](#note) |
| Add a CubeRegion | Depends | See [Note](#note) |
| Remove a CubeRegion | Depends | See [Note](#note) |
| Modify a CubeRegion's include attribute | Depends | See [Note](#note) |
| Add a KeyValue to a CubeRegion | Depends | See [Note](#note) |
| Remove a KeyValue from a CubeRegion | Depends | See [Note](#note) |
| Modify a KeyValue's id | Depends | See [Note](#note) |
| Modify a KeyValue's include attribute | Depends | See [Note](#note) |
| Modify a KeyValue's removePrefix attribute | Depends | See [Note](#note) |
| Modify a KeyValue's validFrom | Depends | See [Note](#note) |
| Modify a KeyValue's validTo | Depends | See [Note](#note) |
| Modify KeyValue's Value's cascadeValues attribute | Depends | See [Note](#note) |
| Modify KeyValue's Value's xml:lang attribute | Depends | See [Note](#note) |
| Modify KeyValue's Value's validFrom | Depends | See [Note](#note) |
| Modify KeyValue's Value's validTo | Depends | See [Note](#note) |
| Modify KeyValue's TimeRange | Depends | See [TimeRange Related Actions](#timerange-related-actions) |
| Switch KeyValue from using TimeRange to Value | Depends | See [Note](#note) |
| Switch KeyValue from using Value to TimeRange | Depends | See [Note](#note) |
| Add Component to CubeRegion | Depends | See [Note](#note) |
| Remove Component from CubeRegion | Depends | See [Note](#note) |
| Modify Component's id | Depends | See [Note](#note) |
| Modify Component's include attribute | Depends | See [Note](#note) |
| Modify Component's removePrefix attribute | Depends | See [Note](#note) |
| Modify Component's Value's cascadeValues attribute | Depends | See [Note](#note) |
| Modify Component's Value's xml:lang attribute | Depends | See [Note](#note) |
| Modify Component's Value's validFrom | Depends | See [Note](#note) |
| Modify Component's Value's validTo | Depends | See [Note](#note) |
| Modify Component's TimeRange | Depends | See [TimeRange Related Actions](#timerange-related-actions) |
| Switch Component from using TimeRange to Value | Depends | See [Note](#note) |
| Switch Component from using Value to TimeRange | Depends | See [Note](#note) |

### TimeRange Related Actions

| Action | Minimum Version Change | Comments|
|--------|:--------------:|---------|
| Modify BeforePeriod | Depends | See [Note](#note) |
| Modify AfterPeriod | Depends | See [Note](#note) |
| Modify StartPeriod | Depends | See [Note](#note) |
| Modify EndPeriod | Depends | See [Note](#note) |
| Modify validFrom | Depends | See [Note](#note) |
| Modify validTo | Depends | See [Note](#note) |
| Switch from using BeforePeriod or AfterPeriod to StartPeriod and EndPeriod | Depends | See [Note](#note) |
| Switch from using StartPeriod and EndPeriod to BeforePeriod or AfterPeriod | Depends | See [Note](#note) |
| Switch from using BeforePeriod to AfterPeriod | Depends | See [Note](#note) |
| Switch from using AfterPeriod to BeforePeriod | Depends | See [Note](#note) |

### Note

If the action results in a more restrictive constraint, then it should be a major change. If the action results in a less restrictive constraint, then it should be a minor change. If the action does not impact the restrictiveness of the constraint, i.e. it is simply a reformulation of the constraint, then it should be a patch.

## Wildcarding Considerations

A DataConstraint can reference other versionable artefacts in their ConstraintAttachment references.
The following are the versionable artefacts which can occur in a ConstraintAttachment:

* DataProvider
* DataStructure
* Dataflow
* ProvisionAgreement  

### Referenced artefact within ConstraintAttachment

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | If minor wildcarding is used then care should be taken to ensure that the DataConstraint is designed in such a way that there is no concern when new fields are added to the supporting referenced artefact. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the referenced artefact within ConstraintAttachment. The definition of the constraint may contain elements which are no longer part of the referenced artefact. For example, a Dimension could have been removed from a DataStructure. |
