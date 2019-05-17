# Muffin Tools Docs - `IUpdatable`

Interface for making *Update Machine* aware of a component.

You must implement this interface in order to make a component work with *Update Machine* system.

## Structure

```cs
public interface IUpdatable
{
    void OnUpdate(float _DeltaTime, float _Factor);

    UpdatableSettings UpdatableSettings { get; }
}
```

---

```cs
void OnUpdate(float _DeltaTime, float _Factor)
```

Called by updated layers from `UpdateMachine` component.

* `float _DeltaTime`: Elapsed time since the last update
* `float _Factor`: For frame and fixed update layers, this value is a multiplier that you can use as you wish. For custom update layers, this factor is already applied when OnUpdate() is called

---

```cs
UpdatableSettings UpdatableSettings { get; }
```

Gets the settings of this updatable.