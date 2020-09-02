# Extensions | DateTime

Namespace: System
Assembly: System.Runtime.dll

The `DateTime` type is a `Struct` that represents an instant in time, typically expressed as a date and time of day.
<br>


## Between()

Verifies if the date is between the interval of two dates.

### Source

```csharp

public static bool Between(this DateTime dt, DateTime start, DateTime end)
{
    return dt.Ticks >= start.Ticks && dt.Ticks <= end.Ticks;
}

```

### Usage

```csharp

TODO: code samples

```

