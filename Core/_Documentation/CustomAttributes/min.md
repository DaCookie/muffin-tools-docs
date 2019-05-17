# Muffin Tools Docs - `MinAttribute`

Locks the value of the property to a given minimum value.

This attribute can be used on these following property types:

- `float`
- `int`
- `Vector2`: locks both x and y to minimum value
- `Vector3`: locks x, y and z to minimum value

## Usage

```cs
public class AttributeTester : MonoBehaviour
{
    // The value can't be less than -1.
    [Min(-1)]
    public float myProperty;
}
```

## Classes

### `MinAttribute`

```cs
public class MinAttribute : PropertyAttribute
```

Contains all settings for the custom property drawer (see below).

#### Constructors

```cs
public MinAttribute(float _Max)
public MinAttribute(int _Max)
```

Creates a `MinAttribute` instance that locks the value of the target property to given value.

---

#### Accessors

```cs
public float Max { get; }
```

Gets the minimum value.

### `MinDrawer`

```cs
[CustomPropertyDrawer(typeof(MinAttribute))]
public class MinDrawer : PropertyDrawer
```

Custom property drawer for the `MinAttribute`.

**This is an Editor class, and should not be called out of the Unity editor.**

#### Methods

```cs
public override void OnGUI(Rect _Position, SerializedProperty _Property, GUIContent _Label)
```

Overrides the property's value if necessary, and draws the property field.