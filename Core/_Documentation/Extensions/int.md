# Muffin Tools Docs - `IntExtension`

Extension methods for `int` values.

## Methods

```cs
public static string AddLeading0(this int _Number, int _Pow)
```

Adds leading 0 before the given number.

**Note that it works only with positive numbers.** If you give a negative number, its absolute value will be used.

* `int _Number`: The number you want to add leading 0.
* `int _Pow`: Number of 0 to eventually add.

Examples:

```cs
private void Test()
{
    Debug.Log(12.AddLeading0(1)); // Logs 12
    Debug.Log(12.AddLeading0(2)); // Logs 12
    Debug.Log(12.AddLeading0(4)); // Logs 0012
}
```