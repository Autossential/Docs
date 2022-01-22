The *Autossential.Configuration.Activities* provides features to handle configuration files (YAML/JSON) which results on the ConfigSection class.

In UiPath's world, we usually see the configurations be stored in workbook files ".xlsx" which I personally don't like because it requires some specific application that requires be installed or external accessed in case we want edit it. (Excel, LibreOffice, Google Sheets, etc)

Using a text file that can be opened by any text editor seems to me a be a better approach.

This activity set was created with this in mind and the only requirement here is format the text file to YAML or JSON standards.

For those who prefer use ".xlsx" but also want the features of ConfigSection class, you can use the provided adapters [DataTable To Config](DataTable To Config.md) or [Dictionary To Config](Dictionary To Config.md) to achieve that.

This package has the following dependencies:

- System.Text.Json (6.0.0)
- YamlDotNet (11.2.1)

!!! info
    Read more about [ConfigSection](_config-section.md) class.
