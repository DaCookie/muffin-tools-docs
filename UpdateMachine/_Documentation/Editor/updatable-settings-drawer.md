# Muffin Tools Docs - `UpdatablesSettingsDrawer`

Property drawer for `UpdatableSettings`, allowing you to selct udpate layer of a component using a proper context menu.

## Methods

```cs
public override void OnGUI(Rect _Position, SerializedProperty _Property, GUIContent _Label)
```

Called when a serialized property of type `UpdatableSettings` is drawn in the inspector.

## Accessors

```cs
public override float GetPropertyHeight(SerializedProperty _Property, GUIContent _Label)
```

Called before a serialized property of type `UpdatableSettings` is drawn in the inspector.

Returns the height (in pixels) or the field in the inspector.