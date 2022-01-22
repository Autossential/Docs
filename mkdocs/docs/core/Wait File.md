Waits until the file be available.

<div class="files-sprite wait-file"></div>

##### Properties

|Name        |Description                                                                                                                                                                           |
|------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|FileInfo    |(Optional) Returns the information about the file.                                                                                                                                    |
|FilePath    |The storage path of the file.                                                                                                                                                         |
|Interval    |Specifies the amount of time (in milliseconds) for the file re-check. Any values out of the range of 100-30000 milliseconds is reseted to its nearest limit. The default value is 500.|
|Timeout     |The maximum timeout to wait in milliseconds.                                                                                                                                          |
|WaitForExist|Waits until the file exists.                                                                                                                                                          |


##### Usage

There are two very common situations where we can use this activity.

- Waiting for some downloading file be completed.
- Waiting for some file in use for another person or process be released.

!!! note
    For files that you **can't** determine the name, [Wait Dynamic File](Wait Dynamic File.md) suits better.

