Converts a DataRow to Dictionary.

<div class="data-table-sprite datarow-to-dictionary"></div>

##### Properties

|Name            |Description           |
|----------------|----------------------|
|InputDataRow    |The input DataRow.    |
|OutputDictionary|The output Dictionary.|


##### Usage

When we need to iterate through a DataTable rows and add them to an Orchestrator Queue we can convert each DataRow to Dicionary and then, pass it to *.ItemInformationCollection* property of the UiPath's *AddQueueItem* activity.