# Extensions | IEnumerable<T>

Namespace: System.Collections.Generic
Assembly: System.Collections.dll

The ÌEnumerable<T>` interface exposes an enumerator mechanism, which supports simple iteration over a collection of a specified type.
<br>


## SecondLast()

Gets the second-last item of a collection.

### Source

```csharp

public static T SecondLast<T>(this IEnumerable<T> source) => source.Reverse().Skip(1).Take(1).First();

```

### Example

```csharp

TODO: Code example

```