# Extensions | Stream

Namespace: System.IO
Assembly: System.Runtime.dll

The `Stream` abstract class provides a generic view of a sequence of bytes.
<br>


## ToByteArray()

Converts a stream object to a byte array.

### Source

```csharp

    public static byte[] ToByteArray(this Stream source)
    {
        using (var ms = new MemoryStream())
        {
            source.CopyTo(ms);

            return ms.ToArray();
        }
    }

```

### Usage

```csharp

    public static void Main()
    {
        ...
        
        Console.WriteLine("The result of the conversion: ");
        Console.WriteLine("    {0}\n", ...);
    }

    // The example displays output like the following:
    //     ...
    //         ...

```