# Muffin Tools Docs - `EditorHelpers`

Bundle of utility methods for Editor operations.

## Constants

```cs
public const string ASSETS_FOLDER = "Assets"
```

---

```cs
public const string RESOURCES_FOLDER = "Resources"
```

---

```cs
public static readonly float HORIZONTAL_MARGIN = EditorGUIUtility.standardVerticalSpacing
```

Default Muffin Tools' editor tools horizontal margin.

---

```cs
public static readonly float VERTICAL_MARGIN = EditorGUIUtility.standardVerticalSpacing
```

Default Muffin Tools' editor tools vertical margin.

---

```cs
public static readonly float LINE_HEIGHT = EditorGUIUtility.singleLineHeight
```

Default Muffin Tools' editor tools property line height.

---

```cs
public const float EDITOR_WINDOW_PADDING = 2f
```

Default Muffin Tools' editor windows padding.

## Generic helpers

```cs
public static void FocusAsset(Object _Object, bool _SelectAsset = true, bool _PingAsset = true)
```

Focuses the given object in the project view, by selecting it and/or highlight it in the Project view.

---

```cs
public static void CreateProjectFolder(string _AssetsRelativePath)
```

Creates a folder in this project if it doesn't exist.

---

```cs
public static EditorWindow FindEditorWindow(string _WindowTitle)
```

Gets the EditorWindow instance of the named window.

* `string _WindowTitle`: The name of the window to get. For example, you can get the Inspector view by passing "Inspector" as parameter

---

```cs
public static Type GetPropertyType(SerializedProperty _Property)
```

Gets the C# type of the given SerializedProperty.

Returns the found property type, or null if the property path can't be used to get final type.

## Assets helpers

```cs
public static AssetCreationResult CreateAsset
(
    Type _AssetType,
    string _FileName = "",
    string _RelativePath = "",
    string _FileExtension = "asset",
    bool _FocusAsset = true
)
```

Creates an asset of the given type.

* `Type _AssetType`: The type of the asset to create
* `string _FileName = ""`: Default name of the asset file
* `string _RelativePath = ""`: Default path to the folder of the asset file
* `string _FileExtension = "asset"`: Default extension of the asset file
* `bool _FocusAsset = true`: Defines if the asset should be selected and highlighted in the Project view after its creation

---

```cs
public static AssetCreationResult CreateAsset<TAssetType>
(
    string _FileName = "",
    string _RelativePath = "",
    string _FileExtension = "asset",
    bool _FocusAsset = true
)
```

Creates an asset of the given type.

* `<TAssetType>`: The type of the asset to create
* `string _FileName = ""`: Default name of the asset file
* `string _RelativePath = ""`: Default path to the folder of the asset file
* `string _FileExtension = "asset"`: Default extension of the asset file
* `bool _FocusAsset = true`: Defines if the asset should be selected and highlighted in the Project view after its creation

---

```cs
public static AssetCreationResult CreateAssetPanel
(
    Type _AssetType,
    string _PanelTitle = "Save new asset",
    string _FileName = "",
    string _DefaultPath = "",
    string _FileExtension = "asset",
    bool _FocusAsset = true
)
```

Creates an asset of the given type, using a Save File Panel.

* `Type _AssetType`: The type of the asset to create
* `string _PanelTitle = "Save new asset"`: Title of the save file popup
* `string _FileName = ""`: Default name of the asset file
* `string _RelativePath = ""`: Default path to the folder of the asset file
* `string _FileExtension = "asset"`: Default extension of the asset file
* `bool _FocusAsset = true`: Defines if the asset should be selected and highlighted in the Project view after its creation

---

```cs
public static AssetCreationResult CreateAssetPanel<TAssetType>
(
    string _PanelTitle,
    string _FileName = "",
    string _DefaultPath = "",
    string _DefaultFileExtension = "asset",
    bool _FocusAsset = true
)
```

Creates an asset of the given type, using a Save File Panel.

* `<TAssetType>`: The type of the asset to create
* `string _PanelTitle = "Save new asset"`: Title of the save file popup
* `string _FileName = ""`: Default name of the asset file
* `string _RelativePath = ""`: Default path to the folder of the asset file
* `string _FileExtension = "asset"`: Default extension of the asset file
* `bool _FocusAsset = true`: Defines if the asset should be selected and highlighted in the Project view after its creation

## Path helpers

```cs
public static string GetAssetAbsolutePath(Object _Asset)
```

Gets the absolute path to the given asset.

---

```cs
public static string GetAssetAbsolutePath(int _InstanceID)
```

Gets the absolute path to the asset that has the given instance ID.

---

```cs
public static string GetAssetAbsolutePath(string _RelativePath)
```

Gets the absolute path, from a given relative path to the current Unity project.

---

```cs
public static bool IsPathRelativeToCurrentProjectFolder(string _AbsolutePath)
```

Checks if the given path points to a folder of the current Unity project.

---

```cs
public static string GetPathRelativeToCurrentProjectFolder(string _AbsolutePath, bool _IncludeAssetsFolder = true)
```

Gets a path relative to this project's Assets folder from a given absolute path. Note that this method will write a log if the given path is not valid.

---

```cs
public static string GetResourcesPath(string _AbsolutePath, string _ExpectedExtension, bool _IncludeResourcesFolder = false)
```

Gets the path to the asset pointed by the given absolute path, from Resources folder of this project.

## GUI helpers

```cs
public static float FloatField(Rect _Position, Rect _DragHotZone, float _Value)
```

Makes a text field for entering floats (just as `EditorGUI.FloatField()`), but allows you to define the "drag hot zone" of the control.

## Editor styles helpers

```cs
public static GUIStyle ReorderableListHeaderStyle
```

Returns the Unity's reorderable lists style.