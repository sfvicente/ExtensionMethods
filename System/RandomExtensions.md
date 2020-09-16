# Extensions | Object

Namespace: System
Assembly: System.Runtime.Extensions.dll

The `Random` class represents a pseudo-random number generator, which is an algorithm that produces a sequence of numbers that meet certain statistical requirements for randomness.
<br>


## OneOf()

Returns a random element from a sequence of items.

### Source

```csharp

    public static T OneOf<T>(this Random source, params T[] values)
    {
        return values[source.Next(values.Length)];
    }

```

### Usage

```csharp

    public static void Main()
    {
        string randomNumber = random.OneOf(42, 201, 88, 17);
	    string randomString = random.OneOf("hearts", "spades", "diamonds", "clubs");
	    object randomObject = random.OneOf(45, "administrator", DateTime.Now, new object());
   
        Console.WriteLine("The result of random elements: ");
        Console.WriteLine("    {0}\n", randomNumber);
        Console.WriteLine("    {0}\n", randomString);
        Console.WriteLine("    {0}\n", randomObject);
    }

    // The example displays output like the following:
    //     ...
    //         ...

```