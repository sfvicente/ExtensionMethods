# Extensions | HttpContextBase

Namespace: System.Web
Assembly: System.Web.dll

The `HttpContextBase` class serves as the base class for classes that contain HTTP-specific information about an individual HTTP request.
<br>


## GetDomain()

Retrives the current domain.

### Source

```csharp

    public static string GetDomain(this HttpContext context)
    {
        return context.Request.Url.GetLeftPart(UriPartial.Authority);
    }

```

### Usage

```csharp

TODO: code samples

```

