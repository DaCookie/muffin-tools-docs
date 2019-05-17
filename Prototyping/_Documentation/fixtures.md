# Muffin Tools Docs - `Fixtures`

Utility class for generating fixtures (random strings, names, numbers, ...).

## Constants

```cs
public const string NUMBERS = "0123456789"
```

```cs
public const string LETTERS = "abcdefghijklmnopqrstuvwxyz"
```

```cs
public const string BASIC_SYMBOLS = "-_."
```

```cs
public const string ADVANCED_SYMBOLS = "&?!,;#{}()[]"
```

```cs
public static readonly string[] FIRST_NAMES =
{
    "John", "Peter", "Steven", "Chuck", "Sergio",
    "Victor", "Tony", "Alonso", "Raymond", "Dimitri",
    "Josy", "Fanny", "Amanda", "Helen", "Maia",
    "Asher", "Olivia", "Atticus", "Amelia", "Jack",
    "Charlotte", "Theodore", "Isla", "Oliver", "Isabella",
    "Jasper", "Cora", "Levi", "Violet", "Arthur",
    "Mia", "Thomas", "Elizabeth", "Rachel", "Tom"
}
```

```cs
public static readonly string[] LAST_NAMES =
{
    "Doe", "Bar", "Simpson", "Henry", "Falcone",
    "Norris", "Harris", "Foo", "Kale", "Fisher",
    "Stark", "Valentine", "Brown", "Amber", "Marston",
    "Stone", "Parker", "Fake", "Wayne", "Gold"
}
```

## Methods

```cs
public static string GenerateString(int _Length, string _PossibleChars)
```

Generates a random string of the given length, using the given possible characters.

---

```cs
public static string GenerateFirstName()
```

Generates a random first name.

---

```cs
public static string GenerateLastName()
```

Generates a random last name.

---

```cs
public static string GenerateFullName(string _Separator = " ")
```

Generates a string that contains random first and last names.

* `string _Separator = " "`: The character or string between first and last names in the output string

---

```cs
public static int GenerateNumber(int _Min, int _Max)
```

Generates a random number between min (inclusive) and max (exclusive).