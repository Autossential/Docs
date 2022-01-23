# Versions Troubleshoot

For all activities that are present in both package versions (2.x and 3.x) you will find one of these blocks:

!!! success "Versions 3.x and 2.x are compatible"

or

!!! warning "Versions 3.x and 2.x are incompatible"

    What was change and how to solve.

### Handling the incompatibility issues

Lets take [Wait Dynamic File](core/Wait Dynamic File.md) for example, we get:

!!! warning "Versions 3.x and 2.x incompatible"

    The XAML property AfterCreationTime is no longer valid.
    
    The XAML property FileInfo is now Result.

This means that if you open a workflow with this activity it will break and some changes need to be done in XAML file.

In 2.x versions, it is:

``` xml
<aa:WaitDynamicFile 
    AfterCreationTime="{x:Null}" 
    ContinueOnError="{x:Null}" 
    SearchPattern="{x:Null}" 
    DirectoryPath="[myDirectoryPath]" 
    DisplayName="Wait Dynamic File" 
    FileInfo="[myFileInfo]" 
    Interval="500" 
    Timeout="30000"
    ... />
```

In 3.x versions, it is:

```xml
<aa:WaitDynamicFile 
    ContinueOnError="{x:Null}" 
    SearchPattern="{x:Null}" 
    DirectoryPath="[myDirectoryPath]" 
    DisplayName="Wait Dynamic File" 
    Result="[myFileInfo]" 
    Interval="500" 
    Timeout="30000"
    ... />
```

To fix the compatibility issue for this activity, we need to update the XAML file by removing the **AfterCreationTime** property and rename **FileInfo** to **Result**.