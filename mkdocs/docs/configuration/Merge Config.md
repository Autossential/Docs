Merges two ConfigSection objects in a way that the destination object values are overwritten by the source object. This also applies to sub-sections.

<div class="config-sprite merge-config"></div>

##### Properties

|Name       |Description                                                                                                                |
|-----------|---------------------------------------------------------------------------------------------------------------------------|
|Destination|The ConfigSection object to which the source ConfigSection is merged.                                                      |
|Override   |Determines if the source values will override the destination values if they already exists. This value is true by default.|
|SectionName|If defined, creates a sub-section to destination object with the name specified and merge the values to it.                |
|Source     |The ConfigSection object to be added to the destination ConfigSection.                                                     |

