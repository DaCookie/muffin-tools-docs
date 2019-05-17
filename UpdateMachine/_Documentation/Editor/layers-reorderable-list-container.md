# Muffin Tools Docs - `LayersReorderableListContainer`

Contains a Reorderable List for a given `UpdateMachineLayer` value as `SerializedProperty`.

## Constructor

```cs
public LayersReorderableListContainer(string _Label, SerializedProperty _Property, bool _UseCustomUpdate = false)
```

Creates an instance of LayersReorderableListContainer.

* `string _Label`: Label of the Reorderable list in the inspector
* `SerializedProperty _Property`: The serialized property that contains the `UpdateMachineLayer` value
* `bool _UseCustomUpdate = false`: Defines if the field uses a custom update timing

## Methods

```cs
public void DoLayoutList()
```

Draws the GUI of the Reorderable List for the `UpdateMachineLayer` instance.