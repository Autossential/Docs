{{activity-description}}

<div class="workflow-sprite next"></div>

##### Properties

{{activity-properties}}

##### Usage

This activity can be only used inside the **Iterate** activity and it is equivalent to `continue` in a for loop, e.g in C#:


``` csharp
for (int i = 0; i < 10; i++)
{
    // ...

    continue;
    
    // ...
}
```


!!! info "Related Activies"
    - [Next](Next.md)
    - [Exit](Exit.md) 
    - [Iterate](Iterate.md)