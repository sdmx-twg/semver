# StructureMap

## Actions

See [General Recommendations for Maintainable Artefacts](../General%20Recommendations%20for%20Maintainable%20Artefacts.md) for other actions.

| Action | Minimum Version Change | Comments|
|--------|:----------------------:|---------|
| Modify the Source | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| Modify the Target | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| EpochMap-related actions | Minor | Changes can impact the output data. See [EpochMap-related actions](#epochmap-related-actions) for listing of all actions. |
| DatePatternMap-related actions | Minor | Changes can impact the output data. See [DatePatternMap-related actions](#datepatternmap-related-actions) for listing of all actions. |
| FrequencyFormatMapping-related actions | Minor | Changes can impact the output data. See [FrequencyFormatMapping-related actions](#frequencyformatmapping-related-actions) for listing of all actions. |
| Modify a ComponentMap's RepresentationMap reference | Depends | See [Changing an artefact reference](../General%20Recommendations%20for%20Maintainable%20Artefacts.md#changing-an-artefact-reference) for details. |
| Other ComponentMap-related actions | Minor | Changes can impact the output data. See [Other ComponentMap-related actions](#other-componentmap-related-actions) for listing of all actions. |
| FixedValueMap-related actions | Minor | Changes can impact the output data. See [FixedValueMap-related actions](#fixedvaluemap-related-actions) for listing of all actions.  |

### EpochMap-related actions

| Action |
|--------|
| Add an EpochMap |
| Remove an EpochMap |
| Modify an EpochMap |
| Add a Source to an EpochMap |
| Remove a Source from an EpochMap |
| Modify an EpochMap's Source |
| Add a Target to an EpochMap |
| Remove a Target from an EpochMap |
| Modify an EpochMap's Target |
| Modify an EpochMap's TargetFrequencyID  |
| Modify an EpochMap's FrequencyDimension |
| Add MappedFrequencies to an EpochMap |
| Remove MappedFrequencies from an EpochMap |
| Modify an EpochMap's MappedFrequencies |
| Switch an EpochMap to use TargetFrequencyID |
| Switch an EpochMap to not use TargetFrequencyID |
| Add resolvePeriod to an EpochMap |
| Remove resolvePeriod from an EpochMap |
| Modify an EpochMap's resolvePeriod |
| Modify an EpochMap's basePeriod |
| Modify an EpochMap's epochPeriod |

### DatePatternMap-related actions

| Action |
|--------|
| Add a DatePatternMap |
| Remove a DatePatternMap |
| Add a Source to a DatePatternMap |
| Remove a Source from a DatePatternMap |
| Modify a DatePatternMap's Source |
| Add a Target to a DatePatternMap |
| Remove a Target from a DatePatternMap |
| Modify a DatePatternMap's Target |
| Modify TargetFrequencyID in a DatePatternMap |
| Modify FrequencyDimension in a DatePatternMap |
| Add MappedFrequencies to a DatePatternMap |
| Remove MappedFrequencies from a DatePatternMap |
| Modify a DatePatternMap's MappedFrequencies |
| Switch a DatePatternMap to use TargetFrequencyID |
| Switch a DatePatternMap to not use TargetFrequencyID |
| Add resolvePeriod to a DatePatternMap |
| Remove resolvePeriod from a DatePatternMap |
| Modify a DatePatternMap's resolvePeriod in DatePatternMap |
| Modify DatePatternMap's sourcePattern |
| Modify DatePatternMap's locale |

### FrequencyFormatMapping-related actions

| Action |
|--------|
| Add a FrequencyFormatMapping |
| Remove a FrequencyFormatMapping |
| Modify a FrequencyFormatMapping's FrequencyId |
| Modify a FrequencyFormatMapping's DatePattern |

### Other ComponentMap-related actions

| Action |
|--------|
| Add a ComponentMap |
| Remove a ComponentMap |
| Add a Source to a ComponentMap |
| Remove a Source from a ComponentMap |
| Modify a ComponentMap's Source |
| Add a Target to a ComponentMap |
| Remove a Target from a ComponentMap |
| Modify a ComponentMap's Target |

### FixedValueMap-related actions

| Action |
|--------|
| Add a FixedValueMap |
| Remove a FixedValueMap |
| Modify a FixedValueMap's Source |
| Modify a FixedValueMap's Target |
| Switch a FixedValueMap from using Source to Target |
| Switch a FixedValueMap from using Target to Source |
| Add a value to a FixedValueMap |
| Remove a value from a FixedValueMap |
| Modify a FixedValueMap's value |

## Wildcarding Considerations

A StructureMap can reference other versionable artefacts in its Source and Taget references as well as it's RepresentationMap reference within its ComponentMap.

### Source References

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | ⚠️ | With a minor wildcard Elements of the Source may be unmapped. For example, if an optional attribute is added to the Source, it would not be mapped to the Target without changing the StructureMap. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of Source references. The mapping described by the StructureMap may become invalid, for example with the removal of a dimension in the Source. |

### Target References

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference in a Target reference. |
| Major | 🟥 | It is not recommended to allow major wildcarding of Target references. The mapping described by the StructureMap may become invalid, for example with the removal of a dimension in the Target. |

### RepresentationMap References within CompotentMaps

| Level |    | Considerations|
|-------|:--:|---------------|
| Minor | 🟢 | There are no concerns with having a minor wildcard reference in a RepresentationMap reference. |  
| Major | 🟥 | It is not recommended to allow major wildcarding of the RepresentationMap references. Changes to the RepresentationMap can make the CompotentMap invalid, for example by removing a source from the RepresentationMap. |
