# Extensions | List<T>

Namespace: System.Collections.Generic
Assembly: System.Collections.dll

A `List` represents a strongly typed group of objects that can be accessed by index with mechanisms to search, sort, and manipulate its elements.
<br>


## IsIn()

Verifies if an element is within a list.

```csharp
public static bool IsIn<T>(this T source, params T[] list)
{
	if(null == source) throw new ArgumentNullException("source");
  
	return list.Contains(source);
}
```

References:
- https://stackoverflow.com/questions/271398/what-are-your-favorite-extension-methods-for-c-codeplex-com-extensionoverflow

### Usage

```csharp

TODO: code samples

```


## IsNotIn()

Verifies if an element is not within a list.

### Source

```csharp

	public static bool IsNotIn<T>(this T source, params T[] list)
	{
		if(null == source)
		{
			throw new ArgumentNullException("source");
		}
	  
		return !list.Contains(source);
	}

```

### Usage

    public static void Main()
    {
        ...
        bool result = number.IsNotIn(list);
	    
        Console.WriteLine("Is the element not within the list? ");
        Console.WriteLine("    {0}\n", );
    }

    // The example displays the following output:
    //     Is the element not within the list? 
    //         ...

