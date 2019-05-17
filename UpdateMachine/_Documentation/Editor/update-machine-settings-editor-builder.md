# Muffin Tools Docs - `UpdateMachineSettingsEditorBuilder`

Contains all data for drawing `UpdateMachineSettings` custom editor.

## Consructor

```cs
public UpdateMachineSettingsEditorBuilder(UpdateMachineSettings _SettingsAsset)
```

Creates an instance of `UpdateMachineSettingsEditorBuilder`, based on the given asset.

## Accessors

```cs
public SerializedProperty FrameUpdateLayersProp { get; }
```

Gets the `UpdateMachineLayer` array for frame update layers, as serialized property.

---

```cs
public SerializedProperty FixedUpdateLayersProp { get; }
```

Gets the `UpdateMachineLayer` array for fixed update layers, as serialized property.

---

```cs
public SerializedProperty CustomUpdateLayersProp { get; }
```

Gets the `UpdateMachineLayer` array for custom update layers, as serialized property.

---

```cs
public SerializedProperty DefaultLayerProp { get; }
```

Gets the default `UpdateMachineLayer` instance, as serialized property.

---

```cs
public LayersReorderableListContainer FrameUpdateLayersList { get; }
```

Gets the `ReordeableList` data for frame update layers.

---

```cs
public LayersReorderableListContainer FixedUpdateLayersList { get; }
```

Gets the `ReordeableList` data for fixed update layers.

---

```cs
public LayersReorderableListContainer CustomUpdateLayersList { get; }
```

Gets the `ReordeableList` data for custom update layers.

---

```cs
public SerializedObject SerializedObject { get; }
```

Gets the `UpdateMachineSettings` asset as serialized object.