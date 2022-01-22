Iterates the activity execution for the specified number of times.

<div class="workflow-sprite iterate"></div>

##### Properties

|Name      |Description                               |
|----------|------------------------------------------|
|Index     |The zero-based iteration index.           |
|Iterations|The number of iterations that must be run.|
|Reverse   |Reverses the order of the output index.   |


##### Usage

The activity is the same as a *for loop* in many languages, e.g in C#:

``` csharp
for (int i = 0; i < 10; i++)
{
    // Do...
}
```

We can use the [Next](Next.md) activity to reproduce the `continue` feature which moves the process to next iteration:

``` csharp
for (int i = 0; i < 10; i++)
{
    // ...

    continue;

    // ...
}
```

And finally, we can use the [Exit](Exit.md) activity to reproduce the `break` feature interrupting the *for loop*:

``` csharp
for (int i = 0; i < 10; i++)
{
    // ...

    break;

    // ...
}
```

!!! info "Related Activies"
    - [Next](Next.md)
    - [Exit](Exit.md) 
    - [Iterate](Iterate.md)