!!! info
    The documentation about this package is still in progress.

The Autossential.Configuration.Activities provides features to handle configuration files (YAML/JSON) which results on the ConfigSection class.

In UiPath's world, we usually see the configurations be stored in workbook files ".xlsx" which requires some specific application be installed or external accessed in case we want edit it. (Excel, LibreOffice, Google Sheets, etc).

A better approach is by using configuration files that can be edit in any text editor already built-in (pre-installed) in the SO (e.g Notepad, TextEdit, Vim/Nano).

This package has activities designed to work with text based configuration files where the only requirement is to have its content formatted to YAML or JSON standards.

For those who prefer use ".xlsx" but also want the features of ConfigSection class, you can use the provided adapters [DataTable To Config](DataTable To Config.md) or [Dictionary To Config](Dictionary To Config.md) to achieve that.

This package has the following dependencies:

- System.Text.Json (6.0.0)
- YamlDotNet (11.2.1)

!!! info
    Read more about [ConfigSection](_config-section.md) class.
