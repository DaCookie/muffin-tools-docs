# Muffin Tools Docs - `UpdateMachineLayerCustom`

Contains informations about a layer, and also all its updatables to update at runtime.

This is an override of [`UpdateMachineLayer`] class for custom update layers.

## Properties

```cs
public const float DEFAULT_CUSTOM_UPDATE_TIME = 1f
```

## Methods

```cs
public override void Tick(float _DeltaTime)
```

Updates the current time of this layer. If it's over the custom update time value, updates each updatables in the list.

---

```cs
public float UpdateTime { get; }
```

Gets the "custom update time" of this layer.