The ConfigSection class encapsulates the raw dictionary from a configuration and provides methods for getting data in the exact type we need, thus simplifying data manipulation.

##### Methods

|     Name      |                       Description                       |
| ------------- | ------------------------------------------------------- |
| AsString      | Retrieves a value as System.String                      |
| AsInt         | Retrieves a value as System.Int32                       |
| AsDouble      | Retrieves a value as System.Double                      |
| AsDecimal     | Retrieves a value as System.Decimal                     |
| AsFloat       | Retrieves a value as System.Float                       |
| AsLong        | Retrieves a value as System.Int64                       |
| AsDateTime    | Retrieves a value as System.DateTime                    |
| AsBoolean     | Retrieves a value as System.Boolean                     |
| AsArray       | Retrieves a value as an array of objects (`object[]`)   |
| AsArray&lt;T> | Retrieves a value as an array of the specified type T   |
| AsList        | Retrieves a value as a list of objects (`List<object>`) |
| AsList&lt;T>  | Retrieves a value as a list of the specified type T     |
| Section       | Retrieves a value as a ConfigSection (aka Sub-Sections) |

##### Usage

Let's take the below YAML configuration as example:

```yaml
ProcessName: MY_BUSINESS_NAME

LocalRecovery:
    MaxRetries: 3
    LogMessage: "Retrying {0} of 3..."

Processes: [CHROME, EXCEL, OUTLOOK]

Credentials:
    System1:
        ServerAddress: "system1.address.com"
        Username: "US1"
    System2:
        ServerAddress: "system2.address.com"
        Username: "US2"
```

_ProcessName_ and _Processes_ are simple keys-value pairs while _LocalRecovery_ and _Credentials_ are configuration sections.

After read this file using [Read Config File](Read Config File.md) activity and get access to ConfigSection object, e.g `Config`, we can retrieve each value as showing on the syntax below:

<div class="two-columns">
    <div>
    Using VB.NET
``` vb.net
Config("Key")
Config("Section/Key")
Config("Section1/Section2/SectionN.../Key")
```
    </div>
    <div>
Using C#
``` C#
Config["Key"]
Config["Section/Key"]
Config["Section1/Section2/SectionN.../Key"]
```
    </div>
</div>

To create a new key-value pair or update you can use:

<div class="two-columns">
    <div>
    Using VB.NET
``` vb.net
Config("NewKey") = "MyValue"
Config("Section/ExistingKey") = 100
Config("Section/NewSection/Key") = { "A", "B" }
```
    </div>
    <div>
Using C#
``` C#
Config["NewKey"] = "MyValue"
Config["Section/ExistingKey"] = 100
Config["Section/NewSection/Key"] = new [] { "A", "B" }
```
    </div>
</div>

When setting a value, in case of a section does not exist it will be created automatically.

By default, all values are boxed on the type `object`. Read more at <a href="https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/types/boxing-and-unboxing" target="_blank">Boxing and Unboxing</a>.

You need then convert the values to the type you need (except Sections) using the conventional way or using the handy methods provided by ConfigSection class, e.g:

Syntaxes are in VB.NET

|                     Conventional                     |           ConfigSection Methods            |
| ---------------------------------------------------- | ------------------------------------------ |
| `Config("ProcessName").ToString`                     | `Config.AsString("ProcessName")`           |
| `CInt(Config("LocalRecovery/MaxRetries"))`           | `Config.AsInt("LocalRecovery/MaxRetries")` |
| `CType(Config("Credentials/System1), ConfigSection)` | `Config.Section("Credentials/System1")`    |



##### Bonus

Below is the same sample configuration in JSON:

``` json
{
  "ProcessName": "MY_BUSINESS_NAME",
  "LocalRecovery": {
    "MaxRetries": 3,
    "LogMessage": "Retrying {0} of 3..."
  },
  "Processes": [
    "CHROME",
    "EXCEL",
    "OUTLOOK"
  ],
  "Credentials": {
    "System1": {
      "ServerAddress": "system1.address.com",
      "Username": "US1"
    },
    "System2": {
      "ServerAddress": "system2.address.com",
      "Username": "US2"
    }
  }
}
```