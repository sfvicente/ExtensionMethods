# Extensions | Environment

Namespace: System
Assembly: System.Runtime.Extensions.dll

The `Environment` class provides information about, and means to manipulate, the current environment and platform.
<br>


## IsWinXPOrHigher()

Determines if the operating system is Windows XP or higher.

## Source

```csharp
public static bool IsWinXPOrHigher(this OperatingSystem OS)
{
  return OS.Platform == PlatformID.Win32NT && (OS.Version.Major > 5 || OS.Version.Major == 5 && OS.Version.Minor >= 1);
}
```

References:
- https://stackoverflow.com/questions/271398/what-are-your-favorite-extension-methods-for-c-codeplex-com-extensionoverflow?page=5

### Usage

```csharp

TODO: code samples

```


## IsWinVistaOrHigher()

Determines if the operating system is Windows Vista or higher.

## Source

```csharp

    public static bool IsWinVistaOrHigher(this OperatingSystem OS)
    {
        return OS.Platform == PlatformID.Win32NT && OS.Version.Major >= 6;
    }

```

References:
- https://stackoverflow.com/questions/271398/what-are-your-favorite-extension-methods-for-c-codeplex-com-extensionoverflow?page=5

### Usage

```csharp

TODO: code samples

```


## IsWin7OrHigher()

Determines if the operating system is Windows 7 or higher.

## Source

```csharp

    public static bool IsWin7OrHigher(this OperatingSystem OS)
    {
      return OS.Platform == PlatformID.Win32NT && (OS.Version.Major > 6 || (OS.Version.Major == 6 && OS.Version.Minor >= 1));
    }

```

References:
- https://stackoverflow.com/questions/271398/what-are-your-favorite-extension-methods-for-c-codeplex-com-extensionoverflow?page=5

### Usage

```csharp

TODO: code samples

```
