# Muffin Tools Docs - `AnimationCurveExtension`

Extension methods for `AnimationCurve` instances.

## Constants & Statics

```cs
public static readonly Keyframe DEFAULT_KEYFRAME = new Keyframe(0f, 0f);
```

Default `Keyframe` used in extension methods.

## Methods

```cs
public static float ComputeDuration(this AnimationCurve _Curve)
```

Calculates the duration of an Animation Curve, using its first and last keyframes on X axis. Note that it will return 0 if the curve counts less than 2 keyframes.

---

```cs
public static float ComputeRange(this AnimationCurve _Curve)
```

Calculates the value range of an Animation Curve, using its lowest and highest keyframes on Y axis. Note that it will return 0 if the curve counts less than 2 keyframes.

---

```cs
public static Keyframe GetFirstKeyframe(this AnimationCurve _Curve)
```

Gets the first keyframe on X axis of the given curve, or `DEFAULT_KEYFRAME` if there's no keyframes on it.

---

```cs
public static float GetMinTime(this AnimationCurve _Curve)
```

Gets the minimum time of this curve.

Returns the found minimum time, or default keyframe's if there's no keyframe on the given curve.

---

```cs
public static Keyframe GetLastKeyframe(this AnimationCurve _Curve)
```

Gets the last keyframe on X axis of the given curve, or `DEFAULT_KEYFRAME` if there's no keyframes on it.

---

```cs
public static float GetMaxTime(this AnimationCurve _Curve)
```

Gets the maximum time of this curve.

Returns the found maximum time, or default keyframe's if there's no keyframe on the given curve.

---

```cs
public static Keyframe GetMinKeyframe(this AnimationCurve _Curve)
```

Gets the lowest keyframe on Y axis of the given curve, or `DEFAULT_KEYFRAME` if there's no keyframes on it.

---

```cs
public static float GetMinValue(this AnimationCurve _Curve)
```

Gets the minimum value of this curve.

Returns the found minimum value, or default keyframe's if there's no keyframe on the given curve.

---

```cs
public static Keyframe GetMaxKeyframe(this AnimationCurve _Curve)
```

Gets the highest keyframe on Y axis of the given curve, or `DEFAULT_KEYFRAME` if there's no keyframes on it.

---

```cs
public static float GetMaxValue(this AnimationCurve _Curve)
```

Gets the maximum value of this curve.

Returns the found maximum value, or default keyframe's if there's no keyframe on the given curve.