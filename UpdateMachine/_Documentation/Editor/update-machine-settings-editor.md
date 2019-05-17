# Muffin Tools Docs - `UpdateMachineSettingsEditor`

Custom editor for `UpdateMachineSettings` asset.

## Subclasses

* [`LayersReorderableListContainer`](./layers-reoderable-list-container.md): Contains a Reorderable List for a given UpdateMachineLayer value as SerializedProperty
* [`UpdateMachineSettingsEditorBuilder`](./layers-reoderable-list-container.md): Contains all data for drawing UpdateMachineSettings custom editor

## Methods

```cs
public override void OnInspectorGUI()
```

Called when `UpdateMachineSettings` asset properties are drawn in the inspector.

---

```cs
public static void DrawUpdateMachineSettings(UpdateMachineSettingsEditorBuilder _Builder)
```

Draws the custom editor of an UpdateMachineSettings asset settings, based on the given builder.

---

```cs
private static void DrawLayerSettings(Rect _Rect, SerializedProperty _LayerProperty, bool _DisableNameEdition = false)
```

Draws all the fields of an `UpdateMachineLayer` instance, given as SerializedProperty.

* `Rect _Rect`: `Rect` container
* `SerializedProperty _LayerProperty`: Serialized `UpdateMachineLayer` property
* `bool _DisableNameEdition = false`: Disable the "layer name" field. Used for default layer editor