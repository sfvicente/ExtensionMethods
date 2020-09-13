# Extensions | Object

Namespace: System
Assembly: System.Runtime.dll

The `Object` class supports all classes in the .NET class hierarchy and provides low-level services to derived classes. It is the root of the type hierarchy.
<br>


## AsOrDefault()

Converts an object to a specific type. If unable to perform the conversion, returns an instance of the target type with the default value.

### Source

```csharp

    public static T AsOrDefault<T>(this object source)
    {
        try
        {
            return (T) source;
        }
        catch (Exception)
        {
            return default(T);
        }
    }

```

### Usage

```csharp

TODO: code samples

```


## ToJson()

Serializes an object to a string containing its JSON representation.

### Source

```csharp

    public static string ToJson(this object source) {
    {
        return JsonSerializer.Serialize(source);
    }

```

Dependencies:
    `System.Text.Json` for the `JsonSerializer` class.
        
### Usage

    public static void Main()
    {
        ...
        string serializedData = obj.ToJson();
	    
        Console.WriteLine("The object serialized to JSON: ");
        Console.WriteLine("    {0}\n", leftText);
    }

    // The example displays the following output:
    //     The object serialized to JSON: 
    //         ...


