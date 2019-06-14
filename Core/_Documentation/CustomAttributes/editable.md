# Muffin Tools Docs - `EditableAttribute`

On property that need an object reference, allow you to select, edit or create an object of the required type directly from the container inspector.

## Usage

`EditableAttribute` works on properties with this type (or inheriting types):

* `ScriptableObject`
* `Component` (and so `MonoBehaviour`)
* `GameObject`

```cs
using UnityEngine;
using MuffinTools;

public class AttributeTester : MonoBehaviour
{
    [Editable]
    public Transform target;

    [Editable]
    public GameObject prefab;
}
```

![`EditableAttribute` example inspector view](./Images/editable-folded.jpg)
![`EditableAttribute` example inspector view (when expanded)](./Images/editable-expanded.jpg)

`Component` objects are *editable*, so you can see a foldout arrow on the left of the `Transform` property. Click on the field's label or the arrow to display the component properties, and edit it directly from the `AttributeTester` component.

On the right of *selectable* fields (such as `Component` or `GameObject` properties), you can see a "*Select*" button. Click on it to select the referenced object in the inspector.

### Usage with `ScriptableObject`

Using `EditableAttribute` on `ScriptableObject`-typed properties allows you to create an asset of that type by clicking on a button. The created asset will be set as the property's object reference value after its creation.

For this example, create a scriptable `UserAsset` that contains basic user data.

```cs
using UnityEngine;
public class UserAsset : ScriptableObject
{
    public string username;
    public int age;
}
```

Now, make a component that can reference a `UserAsset` asset.

```cs
using UnityEngine;
using MuffinTools;
public class UserContainer : MonoBehaviour
{
    [Editable]
    public UserAsset userAsset;
}
```

![`EditableAttribute` example with `ScriptableObject`](./Images/editable-scriptable-object-folded.jpg)

Click on the "*+*" button to create a new `UserAsset`. Select the folder and the name of that new asset, and click "Save". You can see that your new asset is automatically assigned to the property, and you can now edit it directly from `UserContainer` compoonent by clicking on the foldout arrow on the left of the field.

![`EditableAttribute` example  with `ScriptableObject` (when expanded)](./Images/editable-scriptable-object-expanded.jpg)

## Classes

### `EditableAttribute`

```cs
public class EditableAttribute : PropertyAttribute
```

Contains all settings for the custom property drawer (see below).

#### Constructors

```cs
public EditableAttribute()
```

Creates an instance of EditableAttribute.

---

```cs
public EditableAttribute(string _AssetExtension)
```

Creates an instance of EditableAttribute.

* `string _AssetExtension`: If this attribute is used on a `ScriptableObject` field (or an inheriting class), it adds a "*Create Asset*" button in the inspector, which allows you to create a new asset of that field type. The created asset will have the given file extension. By default, the extension is "*asset*"

#### Accessors

```cs
public string ScriptableObjectExtension { get; }
```

Gets the asset extension.

### `EditableDrawer`

```cs
[CustomPropertyDrawer(typeof(EditableAttribute))]
public class EditableDrawer : PropertyDrawer
```

Custom property drawer for the `EditableAttribute`.

**This is an Editor class, and should not be called out of the Unity editor.**

#### Methods

```cs
public override void OnGUI(Rect _Position, SerializedProperty _Property, GUIContent _Label)
```

Displays inspector GUI of the target property.

---

```cs
public override float GetPropertyHeight(SerializedProperty _Property, GUIContent _Label)
```

Gets the height of this property field.

## Enumerations

### `AnimCurveColor`

```cs
public enum EAutoAssignMethod
{
    GetComponent,
    GetComponentInChildren,
    GetComponentInParent,
    GetComponentFromRoot,
    FindObjectOfType
}
```

Defines the component searching method.

* `GetComponent`: use `GetComponent()`
* `GetComponentInChildren`: use `GetComponentInChildren()`
* `GetComponentInParent`: use `GetComponentInParent()`
* `GetComponentFromRoot`: use `GetComponentFromRoot()` extension
* `FindObjectOfType`: use `GameObject.FindObjectOfType()`