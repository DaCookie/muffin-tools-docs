# Muffin Tools Docs - `Updatable`

Abstract component class, shortcut to make an *Update Machine*-dependant component.

This class already implements the `IUpdatable` interface, required to reference the updatable in the *Updata Machine* system. By inheriting this class, all you have to do left is to override the `OnUpdate()` method.

## Usage

```cs
using UnityEngine;
using MuffinTools.UpdateMachine;
public class UpdateMachineTester : Updatable
{
    public override void OnUpdate(float deltaTime, float factor)
    {
        Debug.Log("Updated!");
    }
}
```

- Setup the *Update Machine* (see [Getting started](./README.md))
- Place this component in the scene
- Setup its layer in the editor

## Methods

```cs
public abstract void OnUpdate()
```

Called by updated layers from `UpdateMachine` component.

* `float _DeltaTime`: Elapsed time since the last update
* `float _Factor`: For frame and fixed update layers, this value is a multiplier that you can use as you wish. For custom update layers, this factor is already applied when OnUpdate() is called

---

```cs
protected virtual void OnEnable()
```

Called when this script is enabled (using Unity's message).

Calls `UpdateMachine.AddUpdatable()` to reference the updatable in a layer.

---

```cs
protected virtual void OnDisable()
```

Called when this script is disabled (using Unity's message).

Calls `UpdateMachine.RemoveUpdatable()` to remove this updatable from its layer.

## Accessors

```cs
public UpdatableSettings UpdatableSettings { get; }
```

Gets this updatable's settings (layer and "enabled" state).

[=> More informations about `IUpdatable` interface](./i-updatable)