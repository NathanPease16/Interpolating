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