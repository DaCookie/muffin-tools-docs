# Muffin Tools Docs - `UpdateMachine`

Main component of *Update Machine* system. Contains the `UpdateMachineSettings` asset to use, and updates all layers at runtime.

![Update Machine settings](./Images/um-main-component.jpg)

Note that this class inherits from `MonoSingleton<>`, from Muffin Tools' Core library.

## Usage

You must place a component of this type in your scene (and only one instance) in order to make *Update Machine* work. To add one, from the inspector click on *Add Component > Muffin Tools > Update Machine > Update Machine*.

You also need to create an `UpdateMachineSettings` asset and assign it to the "Update Machine Settings" field. That asset contains all informations about update layers.

[=> More informations about `UpdateMachineSettings` asset](./update-machine-settings.md)

## Methods

```cs
public bool AddUpdatable(IUpdatable _Updatable)
```

Adds an updatable to its target layer. Note that if the updatable's target layer name doesn't exist, it will be added to the default layer.

Returns true if the updatable has successfully been added to a layer, otherwise false.

---

```cs
public bool RemoveUpdatable(IUpdatable _Updatable)
```

Removes the given updatable from its layer.

Returns true if the updatable has successfully been removed from a layer, otherwise false.

---

```cs
public bool ChangeUpdatableLayer(IUpdatable _Updatable, string _TargetLayerName)
```

Removes the given updatable from its layer, then adds it to the given target layer.

Returns true if the operation is successful, otherwise false.

---

```cs
public void ChangeUpdateMachineSettings(UpdateMachineSettings _NewSettings, bool _TransferUpdatables = true)
```

Changes the current UpdateMachineSettings asset.

* `UpdateMachineSettings _NewSettings`: The new settings to use
* `bool _TransferUpdatables = true` Should updatables be transferred to the new layers?

Note that even in the editor, this method is the only way of changing the current `UpdateMachineSettings` asset at runtime.

## Accessors

```cs
public static UpdateMachineSettings Settings { get; set; }
```

Gets the `UpdateMachineSettings` asset on the `UpdateMachine` component instance.
Sets the new `UpdateMachineSettings` asset, using `ChangeUpdateMachineSettings()` method.