Returns an enumerable collection of full file names that match a search pattern (or collection of patterns) and enumeration options in a specified path (or collection of paths).

![](../img/activities/EnumerateFiles.png)

!!! success "Versions 3.x and 2.x are compatible"

##### Properties

|Name         |Description                                                                                                                                                                                                                                                                   |
|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Exclusions   |Excludes from the enumeration the files with any of the specified attributes.                                                                                                                                                                                                 |
|Path         |The relative or absolute path (or collection of paths) to the directory (or directories) to search.                                                                                                                                                                           |
|Result       |An enumerable collection of the full names (including paths) for the files in the directory specified by path and that match the specified search pattern and option.                                                                                                         |
|SearchOption |Specifies whether the search operation should include only the current directory or should include all subdirectories.                                                                                                                                                        |
|SearchPattern|The search string to match against the names of files in path. This parameter can contain a combination of valid literal path and wildcard (\* and ?) characters, but it doesn't support regular expressions. It also supports a collection of strings. Default value is "\*.\*".|


##### Usage

Returns a `IEnumerable<string>` will all file paths from a specified folder.

Use the `SearchPattern` to filter the files by its name or extension.
