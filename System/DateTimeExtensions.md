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


## OrdinalSuffix()

Gets the ordinal suffix of the day of the date.

### Source

```csharp

public static string OrdinalSuffix(this DateTime dateTime)
{
	int day = dateTime.Day;

	if (day % 100 >= 11 && day % 100 <= 13)
	{
		return String.Concat(day, "th");
	}

	switch (day % 10)
	{
		case 1:
			return String.Concat(day, "st");
		case 2:
			return String.Concat(day, "nd");
		case 3:
			return String.Concat(day, "rd");
		default:
			return String.Concat(day, "th");
	}
}

```

### Usage

```csharp

TODO: code samples

```