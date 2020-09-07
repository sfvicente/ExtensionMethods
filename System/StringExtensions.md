# Extensions | String

Namespace: System
Assembly: System.Runtime.dll

The `String` class is a sequential collection of characters that is used to represent text as a sequence of UTF-16 code units.
<br>


## ToSlug()

```csharp
/// <summary>
/// Produces optional, URL-friendly version of a title, "like-this-one". 
/// hand-tuned for speed, reflects performance refactoring contributed
/// by John Gietzen (user otac0n) 
/// </summary>
public static string ToSlug(string title)
{
    if (title == null) return "";

    const int maxlen = 80;
    int len = title.Length;
    bool prevdash = false;
    var sb = new StringBuilder(len);
    char c;

    for (int i = 0; i < len; i++)
    {
        c = title[i];
        if ((c >= 'a' && c <= 'z') || (c >= '0' && c <= '9'))
        {
            sb.Append(c);
            prevdash = false;
        }
        else if (c >= 'A' && c <= 'Z')
        {
            // tricky way to convert to lowercase
            sb.Append((char)(c | 32));
            prevdash = false;
        }
        else if (c == ' ' || c == ',' || c == '.' || c == '/' || 
            c == '\\' || c == '-' || c == '_' || c == '=')
        {
            if (!prevdash && sb.Length > 0)
            {
                sb.Append('-');
                prevdash = true;
            }
        }
        else if ((int)c >= 128)
        {
            int prevlen = sb.Length;
            sb.Append(c.ToAscii());
            if (prevlen != sb.Length) prevdash = false;
        }
        if (i == maxlen) break;
    }

    if (prevdash)
        return sb.ToString().Substring(0, sb.Length - 1);
    else
        return sb.ToString();
}
```

Dependencies:
    Char.ToAscii()

References:
- https://stackoverflow.com/questions/25259/how-does-stack-overflow-generate-its-seo-friendly-urls/

### Usage

```csharp

TODO: code samples

```


##  EqualsIgnoreCase()

Verifies if a string is identical to another string ignoring the casing.

### Source

```csharp

public static bool EqualsIgnoreCase(this string source, string target) => return source.Equals(target, StringComparison.OrdinalIgnoreCase);

```

### Usage

```csharp

TODO: code samples

```


## ToHtmlEncodedString()

Converts the string to an HTML encoded string.

### Source

```csharp

    public static string ToHtmlEncodedString(this string source)
    {
        if (String.IsNullOrEmpty(source))
        {
            return source;
        }

        return HttpUtility.HtmlEncode(source);
    }

```

Dependencies:
    `System.Web` for the `HttpUtility` class.

### Usage

```csharp

TODO: code samples

```


## Compress()

Performs compression of a `String` into a `ByteArray` using the GZip algorithm.

### Source

```csharp

    public static byte[] Compress(this string source)
    {
        byte[] stringAsBytes = Encoding.Default.GetBytes(source);

        using (var memoryStream = new MemoryStream())
        {
            using (var zipStream = new GZipStream(memoryStream, CompressionMode.Compress))
            {
                zipStream.Write(stringAsBytes, 0, stringAsBytes.Length);
                zipStream.Close();

                return (memoryStream.ToArray());
            }
        }
    }

```

Dependencies:
    `System.IO` for the `MemoryStream` class
    `System.IO.Compression` for the `GZipStream` class.

### Usage

```csharp

TODO: code samples

```
