# Extensions | IEnumerable<T>

Namespace: System.Collections.Generic
Assembly: System.Collections.dll

The `IEnumerable<T>` interface exposes an enumerator mechanism, which supports simple iteration over a collection of a specified type.
<br>


## IsEmpty()

Determines if an a collection is empty.

### Source

```csharp

public static bool IsEmpty<T>(this IEnumerable<T> source) => return !source.Any();

```

### Example

```csharp

TODO: Code example

```


## IsNullOrEmpty()

Determines if a collection is null or empty.

### Source

```csharp

 public static bool IsNullOrEmpty<TSource>(this IEnumerable<TSource> source) => return source == null || !source.Any();

```

### Example

```csharp

TODO: Code example

```


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