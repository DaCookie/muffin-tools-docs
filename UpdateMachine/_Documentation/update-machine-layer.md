# Muffin Tools Docs - `UpdateMachineLayer`

Contains informations about a layer, and also all its updatables to update at runtime.

For custom update layers, an instance of [`UpdateMachineLayerCustom`](./pdate-machine-layer-custom.md) is used.

## Constructors

```cs
public UpdateMachineLayer()
```

Creates an instance of `UpdateMachineLayer`.

---

```cs
public UpdateMachineLayer(string _LayerName)
```

Creates an instance of `UpdateMachineLayer` with the given name.

## Methods

```cs
public bool AddUpdatable(IUpdatable _Updatable)
```

Adds the given updatable to this layer, if it's not already in the list.

NOTE: Doesn't care about the `UpdatableSettings` and the updatable's layer name. So you can use this method to manually add updatables to layers.

Returns `true` if the given updatable has successfully been added to this layer, otherwise `false`.

---

```cs
public bool RemoveUpdatable(IUpdatable _Updatable)
```

Removes the given updatable from this layer if it's in the list.

Returns `true` if the given updatable has successfully been removed from this layer, otherwise `false`.

---

```cs
public void Reset()
```

Resets this layer's current time factor, and removes all updatables on it.

---

```cs
public void ResetTimeFactor()
```

Resets this layer's current time factor.

---

```cs
public bool RemoveAllUpdatables(IUpdatable _Updatable)
```

Removes all updatables in the list.

---

```cs
public virtual void Tick(float _DeltaTime)
```

Updates this layer.