{{activity-description}}

![](../img/activities/Aggregate.png)

!!! warning "Versions 3.x and 2.x incompatible"

    The XAML property Detached is no longer valid.

    The Result type is now an array of objects.

##### Properties

=== "3.x"

    {{activity-properties}}

=== "2.x"
    
    {{activity-properties-2x}}

!!! note
    Some aggregate functions are applied just to numeric values while others are applied to all value types, e.g. DistinctCount.

##### Usage

Let's consider the below input DataTable for instance:

| Product | Quantity | Total  |  ID  |
| ------- | -------: | -----: | ---: |
| P-001   |     1000 | 200.25 |  754 |
| P-002   |     1000 | 300.50 |  833 |
| P-003   |      500 | 400.00 |  212 |

Below is the result of **Sum** and **DistinctCoun**t aggregations:

=== "3.x"

    |     Function      |   Result (Object's Array)    |
    | :---------------: | ---------------------------- |
    |      **Sum**      | ``[ , 2500, 900.75, 1799 ]`` |
    | **DistinctCount** | ``[ 3, 2, 3, 3 ]``           |

=== "2.x"

    |     Function      |       Result (DataRow)       |
    | :---------------: | ---------------------------- |
    |      **Sum**      | ``[ , 2500, 900.75, 1799 ]`` |
    | **DistinctCount** | ``[ 3, 2, 3, 3 ]``           |

Note that for **Sum** aggregation, only columns with numeric values has results.<br>
Columns that can't be aggregate by some Function result in *null* values.

We can target specific columns by using the **Columns** property.<br>
For example, setting the value to: ``{"Quantity", "Total Price"}`` or ``{2, 3}``, only these columns are affected:

``[ , 2500, 900.75, ]``

=== "3.x"

    The result output is an array of objects.

    So, if we want add it back to the DataTable as a summary row, just pass it to *ArrayRow* property of the UiPath's Add Data Row Activity.

    ![](../img/Aggregate3x_AddArrayRow.jpg "UiPath's Add Data Row Activity")

=== "2.x"

    By default, the output DataRow is attached to the input DataTable, but you can change it by activating the **Detached** property.

    ![](../img/Aggregate2x_Detached.jpg)

    Being *attached*, means the output DataRow belongs to the input DataTable and any structural changes or data clean up in the DataTable after the use of the Aggregate Activity also affects the output DataRow.

    So, if after the aggregation we resolve add two new columns to our input DataTable, the resulting DataRow will also be affected:

    ``BEFORE: [ , 2500, 900.75, ]``<br>
    ``AFTER:  [ , 2500, 900.75, , , ]``

    In the same way, cleaning up the input DataTable after the aggregation will also clean up our DataRow: 

    ``BEFORE: [ , 2500, 900.75, ]``<br>
    ``AFTER:  [ , , , ]``

    A *detached* DataRow is not affected by these input DataTable changes.

    Another difference between the two modes is regarding adding the output DataRow to the input DataTable.

    While in attached mode you can directly add the DataRow:

    ![](../img/Aggregate2x_AddDataRow.jpg "UiPath's Add Data Row Activity")

    In *detached* mode you need to pass the output DataRow as an array of objects, you can do it by accessing the *.ItemArray* property.

    ![](../img/Aggregate2x_AddArrayRow.jpg "UiPath's Add Data Row Activity")