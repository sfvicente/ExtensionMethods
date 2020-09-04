# Extensions | ICollection<T>

Namespace: System.Collections.Generic
Assembly: System.Runtime.dll

The `ICollection<T>` interface defines methods to manipulate generic collections.
<br>


## AddRange()

Adds the elements of the specified collection to the end of the sequence.

### Source

```csharp

public static void AddRange<T>(this ICollection<T> collection, params T[] items)
{
	foreach (var item in items)
	{
		collection.Add(item);
	}
}

### Usage

```csharp

TODO: code samples

```
