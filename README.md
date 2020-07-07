# C-improvement-ideas
Ideas for how the C language could be improved

## Rethink pre-processor tools
The preprocessor commands in C cause a lot of problems when they go wrong. Often there is no typechecking or even a way of tracking down what something is refering to because it is hidden behind layers of #defines.

#### Uses of #define
#define has 4 main uses:
1. declaring a constant variable
2. adding a switch for conditional compilation
3. declaring a macro
4. alaising a variable

#### The problem with conditional compilation in C
The biggest problem that I have seen has been maintainablity and code readability issues. It is often considered a code smell when conditional compaliation shows up inside of a function. There are other ways that conditional compalation could be handled, especially for functions. 

C# has tried to address this issue by preventing #defines from taking values. This means that a #define is only really useful for an #ifdef statement.

C# has a syntax for specifying if a function should be conditionally compiled:
```C#
[Conditional("CONDITION1")]
public static void Method1(int x)
{
    Console.WriteLine("CONDITION1 is defined");
}
```

