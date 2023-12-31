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

-------------------------------------

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

### Description
Interpolate the value of a float

```cs
public AudioSource audioSource;

void Start()
{
    WiggleWarp.InterpolateFloat(audioSource, "volume", 0f, 1f, 5f);
}
```

-------------------------------------

## InterpolateVector2
```cs
public static int InterpolateVector2<T>(T target, string property, Vector2 goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
```
```cs
public static int InterpolateVector2<T>(T target, string property, Vector2 start, Vector2 goal, float rate, AnimationCurve curve=null, RateMode mode=RateMode.time) where T : class
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

### Description
Interpolate the value of a Vector2

```cs
public float speed = 100f;
public Vector2 goal;
public RectTransform rectTransform;

void ShowUI()
{
    WiggleWarp.InterpolateVector2(rectTransform, "sizeDelta", goal, speed, WiggleWarp.linear, RateMode.speed);
}
```

-------------------------------------

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

### Description
Interpolate the value of a Vector3

```cs
public float time = 3f;
public Vector3 start;
public Vector3 goal;
private bool started;

void Update()
{
    if (Input.GetKeyDown(KeyCode.Alpha1) && !started)
    {
        WiggleWarp.InterpolateVector3(transform, "position", start, goal, time, WiggleWarp.bouncing);
        started = true;
    }
}
```

-------------------------------------

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

### Description
Interpolate the value of a Quaternion

```cs
public float speed = 10f;
public Quaternion upright;
private int id = -1;

void Update()
{
    if (transform.rotation != upright && !WiggleWarp.DoesInterpolationExist(id))
        id = WiggleWarp.InterpolateQuaternion(transform, "rotation", upright, speed, WiggleWarp.linear, RateMode.speed);
}
```

-------------------------------------

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

### Description
Interpolate the value of a Color

```cs
public float time = 2f;
public Material material;

void Update()
{
    if (Input.GetKeyDown(KeyCode.Alpha1))
        WiggleWarp.InterpolateColor(material, "color", Color.white, Color.black, time, WiggleWarp.easeInOut);
}
```

-------------------------------------

## DoesInterpolationExist
```cs
public static bool DoesInterpolationExist(int id)
```
| Parameter | Description |
| - | - |
| id | ID of the interpolation to check |

### Returns
**bool** If the interpolation exists

### Descriptions
When an interpolation is started, it returns an ID associated with it. If that ID is canceled or the interpolation is finished, the interpolation associated with that ID no longer exists

```cs
public float time = 10f;
public Vector3 start;
public Vector3 goal;
private int id = -1;

void Update()
{
    if (!WiggleWarp.DoesInterpolationExist(id))
        id = WiggleWarp.InterpolateVector3(transform, "position", start, goal, time, WiggleWarp.bouncing);
}
```

-------------------------------------

## IsInterpolationPaused
```cs
public static bool IsInterpolationPaused(int id)
```

| Parameter | Description |
| - | - |
| id | ID of the interpolation to check |

### Returns
**bool** If the interpolation is paused

### Description
Determines if the interpolation associated with the given ID is paused or not

```cs
public float time = 2.5f;
public Material material;
public Color start;
public Color goal;
private int id = -1;

void Start()
{
    id = WiggleWarp.InterpolateColor(material, "color", start, goal, time);
}

void Update()
{
    if (Input.GetKeyDown(KeyCode.P) && !WiggleWarp.IsInterpolationPaused(id))
         WiggleWarp.PauseInterpolation(id);
}
```

-------------------------------------

## PauseInterpolation
```cs
public static void PauseInterpolation(int id)
```

| Parameter | Description |
| - | - |
| id | ID of the interpolation to pause |

### Description
Pauses the interpolation associated with the given ID

```cs
public float time = .1f;
public Vector3 start;
public Vector3 goal;
public bool paused;
private int id = -1;

void Start()
{
    id = WiggleWarp.InterpolateVector3(transform, "scale", start, goal, time, WiggleWarp.bouncing);
}

void Update()
{
    if (paused)
        WiggleWarp.PauseInterpolation(id);
    else
        WiggleWarp.ResumeInterpolation(id);
}
```

-------------------------------------

## ResumeInterpolation
```cs
public static void ResumeInterpolation(int id)
```

| Parameter | Description |
| - | - |
| id | ID of the interpolation to resume |

### Description
Resumes the interpolation associated with the given ID

```cs
public float time = 5f;
public Quaternion start;
public Quaternion goal;
private int id = -1;

void Start()
{
    id = WiggleWarp.InterpolateQuaternion(transform, "rotation", start, goal, time);
}

void Update()
{
    if (Input.GetKeyDown(KeyCode.P))
    {
        if (WiggleWarp.IsInterpolationPaused(id))
            WiggleWarp.ResumeInterpolation(id);
        else
            WiggleWarp.PauseInterpolation(id);
    }
}
```

-------------------------------------

## CancelInterpolation
```cs
public static void CancelInterpolation(int id)
```

| Parameter | Description |
| - | - |
| id | ID of the interpolation to cancel |

### Description
Cancels the interpolation associated with the given ID

```cs
public float time = 1.2f;
public Vector2 start;
public Vector2 goal;
public bool paused;
private int id = -1;

void Start()
{
    id = WiggleWarp.InterpolateVector3(transform, "position", start, goal, time, WiggleWarp.recovery);
}

void Update()
{
    if (Input.GetKeyDown(KeyCode.Escape))
        WiggleWarp.CancelInterpolation(id);
}
```
