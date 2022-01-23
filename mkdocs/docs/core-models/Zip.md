{{activity-description}}

![](../img/activities/Zip.png)

!!! warning "Versions 3.x and 2.x incompatible"
   
    The XAML property AutoRenaming is no longer valid.

##### Properties

=== "3.x"

    {{activity-properties}}

=== "2.x"

    {{activity-properties-2x}}

##### Usage

You can specify a single or multiple files and folders to be compressed on `.ToCompress` property:

Compressing specific files:

- `"C:\Temp\file1.docx"`
- `{ "C:\Temp\file1.docx", "C:\Temp\file2.xlsx" }`

Compressing folders:

- `"C:\Temp\Documents"`
- `{ "C:\Temp\Documents", "C:\Temp\Images", "C:\Temp\Musics" }`

Mixing Files and Folders:

- ` { "C:\Temp\file1.docx", "C:\Temp\Musics", "C:\Temp\Images\avagar.png" }`