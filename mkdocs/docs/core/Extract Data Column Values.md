Returns an array with all values of a respective data column.

<div class="data-table-sprite extract-data-column-values"></div>

##### Properties

|Name        |Description                                                                                |
|------------|-------------------------------------------------------------------------------------------|
|Column      |The column name or index where the values will be extracted from.                          |
|DataTable   |The data table where the values will be extracted from.                                    |
|DefaultValue|The value to be use in case of the extract value cannot be converted to the specified type.|
|Result      |The array of values extracted from the data column.                                        |
|TypeArgument|Determines the type of each value extracted from the data column.                          |


##### Usage

Considering below DataTable:

| Name | Age | Country |
| ---- | --- | ------- |
| John | 41  | US      |
| Ana  | 35  | RU      |
| Alex | 38  | BR      |

To extract all values from column "Age" you can pass the column name "Age" or its index 1. 

```[41, 35, 38]```

By default all values are extract as objects resulting in array of objects `object[]`.

In this example, we can specify the type to `Int32` to get an array of integers `Int32[]`

![](../img/activities/extract-data-column-values-type.png)

In some scenarios we can have null values.

| Name | Age | Country |
| ---- | --- | ------- |
| John | 41  | US      |
| Ana  |     | RU      |
| Alex | 38  | BR      |

By default, the activity will resolve it using the default value of the specified type, e.g `default(Int32)`, which in this case will return in zero.

`[41, 0, 38]`

You can use an alternative value by specifying it on `DefaultValue` property. Read more on the properties table above.



