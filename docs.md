# Wiggle Warp Documentation


## Curves
| Curve | Description |
| ----------- | ----------- |
| linear| A linear curve |
| quadratic | A quadratic curve |
| cubic | A cubic curve |
| bouncing | Dips slightly below 0, linearly increases passed 1, and then settles at 1 |
| overshoot | Linearly increases passed 1 and then settles at 1 |
| recovery | Dips below 0 and then linearly increases to 1 |
| easeIn | Eases into a linear line towards 1 |
| easeOut | Eases out of a linear line towards 1 |
| easeInOut| Eases into and out of a linear line towards 1 |


## Public Methods
| Method | Description |
| - | - |
| InterpolateFloat | Interpolates a float from start to goal |
| InterpolateVector2 | Interpolates a Vector2 from start to goal |
| InterpolateVector3 | Interpolates a Vector3 from start to goal |
| InterpolateQuaternion | Interpolates a Quaternion from start to goal |
| InterpolateColor | Interpolates a Color from start to goal |
| DoesInterpolationExist | Does the interpolation exist? |
| IsInterpolationPaused | Is the interpolation currently paused? |
| PauseInterpolation | Pauses an interpolation |
| ResumeInterpolation | Unpauses an interpolation |
| CancelInterpolation | Cancels an interpolation |


## InterpolateFloat
```cs 
public static int InterpolateFloat<T>(T target, string property, float goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
```
```cs 
public static int InterpolateFloat<T>(T target, string property, float start, float goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
```

| Parameter | Description |
| - | - |
| target | The target object to interpolate the property of |
| property | Name of the property to interpolate |
| start | Where the interpolation should start off |
| goal | Desired end value |
| rate | Rate of the interpolation |
| curve | Curve the interpolation should follow |
| mode | The interpolation mode rate should move in |

### Returns
**int** ID of the newly started interpolation


## InterpolateVector2
`public static int InterpolateVector2<T>(T target, string property, Vector2 goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class`
` public static int InterpolateVector2<T>(T target, string property, Vector2 start, Vector2 goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class`

| Parameter | Description |
| - | - |
| target | The target object to interpolate the property of |
| property | Name of the property to interpolate |
| start | Where the interpolation should start off |
| goal | Desired end value |
| rate | Rate of the interpolation |
| curve | Curve the interpolation should follow |
| mode | The interpolation mode rate should move in |

### Returns
**int** ID of the newly started interpolation


## InterpolateVector3
```cs 
public static int InterpolateVector3<T>(T target, string property, Vector3 goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
```
```cs 
public static int InterpolateVector3<T>(T target, string property, Vector3 start, Vector3 goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
```

| Parameter | Description |
| - | - |
| target | The target object to interpolate the property of |
| property | Name of the property to interpolate |
| start | Where the interpolation should start off |
| goal | Desired end value |
| rate | Rate of the interpolation |
| curve | Curve the interpolation should follow |
| mode | The interpolation mode rate should move in |

### Returns
**int** ID of the newly started interpolation


## InterpolateQuaternion
```cs 
public static int InterpolateQuaternion<T>(T target, string property, Quaternion goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
```
```cs 
public static int InterpolateQuaternion<T>(T target, string property, Quaternion start, Quaternion goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
```

| Parameter | Description |
| - | - |
| target | The target object to interpolate the property of |
| property | Name of the property to interpolate |
| start | Where the interpolation should start off |
| goal | Desired end value |
| rate | Rate of the interpolation |
| curve | Curve the interpolation should follow |
| mode | The interpolation mode rate should move in |

### Returns
**int** ID of the newly started interpolation


## InterpolateColor
```cs 
public static int InterpolateColor<T>(T target, string property, Color goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
```
```cs 
public static int InterpolateColor<T>(T target, string property, Color start, Color goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
```

| Parameter | Description |
| - | - |
| target | The target object to interpolate the property of |
| property | Name of the property to interpolate |
| start | Where the interpolation should start off |
| goal | Desired end value |
| rate | Rate of the interpolation |
| curve | Curve the interpolation should follow |
| mode | The interpolation mode rate should move in |

### Returns
**int** ID of the newly started interpolation
