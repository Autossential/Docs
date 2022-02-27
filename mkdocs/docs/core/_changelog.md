# Changelog
All notable changes to this project will be documented in this page.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## 3.0.1 - 2022.02.20

Small fix on **Enumerate Files** activity designer regarding a property binding issue with folder picker.

## 3.0.0 - 2022.02.06

This version is compatible with Windows Legacy (.NET 4.61 Framework) and Windows (.NET 5).

Some standards was adopted from now on resulting in significant **BREAKING CHANGES**.

<pre class="changelog">
ADDED
- Compability with Windows (.NET 5.0)
- When-Do Activity
- New Encryption Activities that were designed in a composition way.
  > Text Encryption
  > DataTable Encryption

CHANGES
- Activities that returns a single value is now deriving from CodeActivity&lt;T>.
- Some XAML property names or structure was changed resulting in a BREAKING CHANGES for the below activities:
  > Aggregate
  > DataRow To Dictionary
  > DataTable To Text
  > Dictionary To DataTable
  > Enumerate Files
  > Extract Data Column Values
  > Promote Headers
  > Remove Data Columns
  > Remove Duplicate Rows
  > Remove Empty Rows
  > Transpose Data
  > Stopwatch
  > Zip
  > Wait File
  > Wait Dynamic File

- Extract Data Column Values: DefaultValue display name fixed.
- Aggregate: Detached option was removed.
- DataTable category is now called Data

REMOVED
- Decrypt DataTable
- Decrypt Text
- Encrypt DataTable
- Encrypt Text
</pre>

## 2.1.1 - 2022.01.03
<pre class="changelog">
CHANGES
- Implementation of cancellation token on Wait Dynamic File activity.
- ContinueOnError fix for asyncronous activities
</pre>


## Older
- 2.1.0 - Obsolete - 2021.12.21
- 2.0.3 - Obsolete - 2021.05.23
- 2.0.2 - Obsolete - 2021.01.08
- 2.0.1 - Obsolete - 2021.01.07
- 2.0.0 - Obsolete - 2020.12.31