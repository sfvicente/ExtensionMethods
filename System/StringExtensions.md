# Extensions | String

Namespace: System
Assembly: System.Runtime.dll

The `String` class is a sequential collection of characters that is used to represent text as a sequence of UTF-16 code units.
<br>


## ToByteArray()

Encodes a set of characters into a sequence of bytes.

### Source

```csharp

public static byte[] ToByteArray(this string source) 
{
    return System.Text.Encoding.Unicode.GetBytes(text);
}

```

Dependencies:
    `System.Text` for the `Encoding` class.

### Usage

```csharp

    public static void Main()
    {
    	string text = "Hello World!";
        byte[] arr = text.ToByteArray();
	    
        Console.WriteLine("The text as a sequence of bytes: ");
        Console.WriteLine("    {0}\n", arr);
    }

    // The example displays the following output:
    //     The text as a sequence of bytes:
    //         ...

```




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


## DecodeBase64()

Decodes a base 64 string.

### Source

```csharp

    public static string DecodeBase64(this string source)
    {
        byte[] base64EncodedData = System.Convert.FromBase64String(source);

        return System.Text.Encoding.UTF8.GetString(base64EncodedData);
    }

```

Dependencies:
    `System.Text` for the `Encoding` class

### Usage

```csharp

    public static void Main()
    {
    	string base64EncodedData = "SGVsbG8gV29ybGQh";
        string base64DecodedData = base64EncodedText.DecodeBase64();
	    
        Console.WriteLine("The base 64 decoded data: ");
        Console.WriteLine("    {0}\n", base64DecodedData);

        // The example displays the following output:
        //     The base 64 decoded data:
        //         Hello World!
    }

```


## EncodeBase64()

Encodes a string to a base 64 representation.

### Source

```csharp

    public static string EncodeBase64(this string source)
    {
        byte[] encodedBase64Data = System.Text.Encoding.UTF8.GetBytes(source);
  
        return System.Convert.ToBase64String(encodedBase64Data);
    }

```

Dependencies:
    `System.Text` for the `Encoding` class

### Usage

```csharp

    public static void Main()
    {
    	string text = "Hello World!";
        string base64EncodedText = text.EncodeBase64();
	    
        Console.WriteLine("The base 64 encoded text: ");
        Console.WriteLine("    {0}\n", encodedBase64);
    }

    // The example displays the following output:
    //     The base 64 encoded text:
    //         SGVsbG8gV29ybGQh

```





## Capitalize()

Converts the first letter of a string to upper case.

### Source

```csharp

    public static string CapitalizeFirstLetter(this String source)
    {
        if(string.IsNullOrEmpty(source))
        {
            return input;
		}     

        return input.Substring(0, 1).ToUpper(CultureInfo.CurrentCulture) + input.Substring(1, input.Length - 1);
    }

```

Dependencies:
    `System.Text` for the `Encoding` class

Notes:
    The method assumes that the first letter is the correct one that needs to change. It is therefore, not culture-safe.

References:
    https://stackoverflow.com/questions/748411/is-there-a-capitalizefirstletter-method

### Usage

```csharp

    public static void Main()
    {
    	string text = "hello world!";
        string capitalizedText = text.Capitalize();
	    
        Console.WriteLine("The capitalized text: ");
        Console.WriteLine("    {0}\n", capitalizedText);
    }

    // The example displays the following output:
    //     The base 64 encoded text:
    //         Hello world!

```


## ParseQuery()

.

### Source

```csharp

    public static NameValueCollection ParseQueryString(this string source)
    {
        return HttpUtility.ParseQueryString(source);
    }

```

Dependencies:
    `System.Web` for the `HttpUtility` class.

### Usage

```csharp

    public static void Main()
    {
        // ToDo: code sample.
    }


```


## ToTitleCase()

Capitalizes first letter of each word, except for certain small words, such as articles and short prepositions.

### Source

```csharp

    public static string ToProperCase(this string text)
    {
        System.Globalization.CultureInfo cultureInfo = System.Threading.Thread.CurrentThread.CurrentCulture;
        System.Globalization.TextInfo textInfo = cultureInfo.TextInfo;
        return textInfo.ToTitleCase(text);
    }

```

Dependencies:
    `System.Threading` for the `Thread` class.
    `System.Globalization` for the `CultureInfo` and `TextInfo` classes.

### Usage

```csharp

    public static void Main()
    {
        // ToDo: code sample.
    }


```


## Left()

Obtains a string containing the specified number of characters from the left side of a string.

### Source

```csharp

    public static string Left(this string source, int length)
    {
        if (string.IsNullOrEmpty(source))
        {
            return null;
        }

        if(length > source.Length)
        {
            length = source.Length;  
		}

        return source.Substring(0, length);
    }

```

### Usage

```csharp

    public static void Main()
    {
    	string text = "Hello world!";
        string leftText = text.Left(5);
	    
        Console.WriteLine("The left part of the text: ");
        Console.WriteLine("    {0}\n", leftText);
    }

    // The example displays the following output:
    //     The left part of the text:
    //         Hello

```


## Right()

Obtains a string containing a specified number of characters from the right side of a string.

### Source

```csharp

    public static string Right(this string source, int length)
    {
        if (string.IsNullOrEmpty(source) || length < 0)
        {
            return null;
        }

        if(length > source.Length)
        {
            length = source.Length;  
		}

        return source.Substring(source.Length - length, length);
    }

```

### Usage

```csharp

    public static void Main()
    {
        // ToDo: code sample.
    }


```


## Mid()

Obtains a string containing a specified number of characters from a string.

### Source

```csharp

    public static string Mid(this string source, int start, int length)
    {
        if (string.IsNullOrEmpty(source) || start < 0 || length < 0)
        {
            return null;
        }

        if(start + length > source.Length)
        {
            length = source.Length - start;  
		}

        return source.Substring(start, length);
    }

```

### Usage

```csharp

    public static void Main()
    {
        // ToDo: code sample.
    }


```


## FromJson()

Deserializes an object from a string containing its JSON representation.

### Source

```csharp

    public static T FromJson<T>(this string source)
    {
        T t = JsonSerializer.Deserialize<T>(source);

        return t;
    }

```

Dependencies:
    `System.Text.Json` for the `JsonSerializer` class.
        
### Usage

    public static void Main()
    {
        ...
        string deserializedData = data.FromJson();
	    
        Console.WriteLine("The object deserialized from JSON: ");
        Console.WriteLine("    {0}\n", );
    }

    // The example displays the following output:
    //     The object deserialized from JSON: 
    //         ...
