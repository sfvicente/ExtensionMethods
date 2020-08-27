# Extensions | Char

Namespace: System
Assembly: System.Runtime.dll

Char is a Struct that represents a character as a UTF-16 code unit.
<br>

## ToAscii()

Replaces international characters such as diacrits with ASCII characters. A common use for this method is to assist creating urls/slugs from strings such as post titles.

```csharp
public static string ToAscii(char c)
{
    string s = c.ToString().ToLowerInvariant();

    if ("àåáâäãåą".Contains(s))
    {
        return "a";
    }
    else if ("èéêëę".Contains(s))
    {
        return "e";
    }
    else if ("ìíîïı".Contains(s))
    {
        return "i";
    }
    else if ("òóôõöøőð".Contains(s))
    {
        return "o";
    }
    else if ("ùúûüŭů".Contains(s))
    {
        return "u";
    }
    else if ("çćčĉ".Contains(s))
    {
        return "c";
    }
    else if ("żźž".Contains(s))
    {
        return "z";
    }
    else if ("śşšŝ".Contains(s))
    {
        return "s";
    }
    else if ("ñń".Contains(s))
    {
        return "n";
    }
    else if ("ýÿ".Contains(s))
    {
        return "y";
    }
    else if ("ğĝ".Contains(s))
    {
        return "g";
    }
    else if (c == 'ř')
    {
        return "r";
    }
    else if (c == 'ł')
    {
        return "l";
    }
    else if (c == 'đ')
    {
        return "d";
    }
    else if (c == 'ß')
    {
        return "ss";
    }
    else if (c == 'Þ')
    {
        return "th";
    }
    else if (c == 'ĥ')
    {
        return "h";
    }
    else if (c == 'ĵ')
    {
        return "j";
    }
    else
    {
        return "";
    }
}
```

There are other standard libraries to achieve a similar effect but this algorithm is quite fast. Speed was one of original requirements as the function would potentially
be called hundreds of times per page.

Although using `switch` is generally faster, the reason this code uses `if-else-if` instead of `switch` is that the sequence of `if` instructions are ordered by frequency
that those letters occur in English. It hits the most common cases first, and almost never reaches the bottom.

Reference: https://meta.stackexchange.com/questions/7435/non-us-ascii-characters-dropped-from-full-profile-url/7696#7696