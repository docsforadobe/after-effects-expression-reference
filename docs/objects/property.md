# Property

This category holds generic entries relating to generic *properties*.

In expressions, a Property is *typically* anything that exists in the timeline (even if it can't be keyframed, or hold an expression).

??? example "Examples of Properties"

    All of the following AE items are actually "Properties" for the use of expressions, along with *some* ways to access those properties by code:

    - Position (`thisLayer.transform.position`, `layer.position`)
    - Scale (`thisLayer.transform.scale`, `layer.scale`)
    - A slider effect's *actual slider* (`effect("Slider Control")("Slider")`, `effect("Slider Control")(1)`)
    - A text layer's [Text](../text/text.md) property (`thisLayer.text`)
        - *Note that in this case, Text also has its own special items, found in the above link.*

!!! info
    On this page, we're going to use `thisLayer.position` as a sample on how to call these items, however note that any method that returns a [Property](#) will work.

---

## Attributes

### name

`thisLayer.position.name`

#### Description

Returns the name of the property or property group.

#### Type

String

---

### numKeys

`thisLayer.position.numKeys`

#### Description

Returns the number of keyframes on a property, or the number of markers on a marker property.

!!! note
    If you use the **Separate Dimensions** command to separate the dimensions of the Position property into individual components, the number of keyframes changes, so the value returned by this method changes.

#### Type

Number

---

### propertyIndex

`thisLayer.position.propertyIndex`

#### Description

Returns the index of a property relative to other properties in its property group, including property groups within masks, effects, text animators, selectors, shapes, trackers, and track points.

#### Type

Number

---

### speed

`thisLayer.position.speed`

#### Description

Returns a 1-dimensional, positive speed value equal to the speed at which the property is changing at the default time.

!!! note
    This can be used only for spatial properties.

#### Type

Number

---

### value

`thisLayer.position.value`

#### Description

Returns the value of a property at the current time.

#### Type

Number, Array, or String

---

### velocity

`thisLayer.position.velocity`

#### Description

Returns the temporal velocity value at the current time. For spatial properties, such as Position, it returns the tangent vector value. The result is the same dimension as the property.

#### Type

Number or Array

---

## Methods

### key()

`thisLayer.position.key(index)`

#### Description

Returns the Key or MarkerKey object by index number.

#### Parameters

| Parameter |  Type  |             Description             |
| --------- | ------ | ----------------------------------- |
| `index`   | Number | The key (or MarkerKey) index number |

#### Returns

Key or MarkerKey

#### Example

To retrieve the first keyframe on a property:

```js
thisLayer.scale.key(1);
```

To retrieve the *last* keyframe on a property:

```js
thisLayer.rotation.key(thisLayer.rotation.numKeys);
```

---

### key()

`thisLayer.position.key(markerName)`

#### Description

Returns the MarkerKey object with this name.

!!! note
    This can be used only on marker properties.

#### Parameters

|  Parameter   |  Type  |                      Description                      |
| ------------ | ------ | ----------------------------------------------------- |
| `markerName` | String | The name of the marker to return the matching key of. |

#### Returns

MarkerKey

---

### loopIn()

`thisLayer.position.loopIn([type="cycle"][, numKeyframes=0])`

#### Description

Loops a segment of time that is measured from the first keyframe on the layer forward toward the Out point of the layer. The loop plays from the In point of the layer.

You can use keyframe-looping methods to repeat a series of keyframes. You can use these methods on most properties. Exceptions include:
    - properties that can't be expressed by simple numeric values in the Timeline panel, such as:
        - the Source Text property,
        - path shape properties, and
        - the Histogram property for the Levels effect.

Keyframes or duration values that are too large are clipped to the maximum allowable value. Values that are too small result in a constant loop.

#### Parameters

|   Parameter    |                           Type                            |                                                                  Description                                                                   |
| -------------- | --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`         | Predefined string as defined in [Loop Types](#loop-types) | Optional. The loop type to use. Defaults to `"cycle"`                                                                                          |
| `numKeyframes` | Number                                                    | Optional. The segment to loop, from keyframe #1 to keyframe #`numKeyframes + 1`. If unspecified (or `0`), all keyframes loop. Defaults to `0`. |

#### Returns

A looped value of the same property type as this current property.

#### Example

**To loop the segment bounded by the first and fourth keyframes:**

```js
loopIn("cycle", 3);
```

**To loop forward and backward indefinitely from your current keyframes:**

```js
loopIn("continue") + loopOut("continue") - value;
```

Note that we need to subtract `value`, because both `loopIn()` and `loopOut()` include the current value; by adding them, we have two copies of the current value, and need to remove one (the ` - value`) to get back to the proper keyframe value.

---

### loopInDuration()

`thisLayer.position.loopInDuration([type="cycle"][, duration=0])`

#### Description

Loops a segment of time that is measured from the first keyframe on the layer forward toward the Out point of the layer.

#### Parameters

| Parameter  |                           Type                            |                                                                                           Description                                                                                            |
| ---------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `type`     | Predefined string as defined in [Loop Types](#loop-types) | Optional. The loop type to use. Defaults to `"cycle"`                                                                                                                                            |
| `duration` | Number                                                    | Optional. The number of composition seconds in a segment to loop, measured from the first keyframe. If unspecified (or `0`), the segment to loop begins at the layer Out point. Defaults to `0`. |

#### Returns

A looped value of the same property type as this current property.

#### Example

**To loop the first second of the entire animation:**

```js
loopInDuration("cycle", 1);
```

---

### loopOut()

`thisLayer.position.loopOut([type="cycle"][, numKeyframes=0])`

#### Description

Loops a segment of time that is measured from the last keyframe on the layer back toward the In point of the layer. The loop plays until the Out point of the layer.

!!! info
    David Van Brink provides an instructional article and sample project on his [omino pixel blog](http://omino.com/pixelblog/2007/11/23/salmonella/) that show how to use the Echo effect, the Particle Playground effect, and the `loopOut()` method to animate a swarm of stylized swimming bacteria.

#### Parameters

|   Parameter    |                           Type                            |                                                              Description                                                               |
| -------------- | --------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| `type`         | Predefined string as defined in [Loop Types](#loop-types) | Optional. The loop type to use. Defaults to `"cycle"`                                                                                  |
| `numKeyframes` | Number                                                    | Optional. The segment to loop, measured backward from the last keyframe. If unspecified (or `0`), all keyframes loop. Defaults to `0`. |

#### Returns

A looped value of the same property type as this current property.

#### Example

**To loop the segment bounded by the last keyframe and second-to-last keyframe:**

```js
loopOut("cycle", 1);
```

---

### loopOutDuration()

`thisLayer.position.loopOutDuration([type="cycle"][, duration=0])`

#### Description

Loops a segment of time that is measured from the last keyframe on the layer back toward the In point of the layer. The loop plays until the Out point of the layer.

#### Parameters

| Parameter  |                           Type                            |                                                                                               Description                                                                                               |
| ---------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`     | Predefined string as defined in [Loop Types](#loop-types) | Optional. The loop type to use. Defaults to `"cycle"`                                                                                                                                                   |
| `duration` | Number                                                    | Optional. The number of composition seconds in a segment to loop, measured backward from the last keyframe. If unspecified (or `0`), the segment to loop begins at the layer In point. Defaults to `0`. |

#### Returns

A looped value of the same property type as this current property.

#### Example

**To loop the last second of the entire animation:**

```js
loopOutDuration("cycle", 1);
```

---

### nearestKey()

`thisLayer.position.nearestKey(t)`

#### Description

Returns the Key or MarkerKey object nearest to a designated time `t`.

#### Parameters

| Parameter |  Type  |              Description              |
| --------- | ------ | ------------------------------------- |
| `t`       | Number | The time to find the nearest key from |

#### Returns

Key or MarkerKey

#### Example

**Get the nearest keyframe to the 2-second time in the comp:**

```js
const twoSecondKey = thisLayer.scale.nearestKey(2);

// and then, to get the value of that key:
twoSecondKey.value;
```

---

### propertyGroup()

`thisLayer.position.propertyGroup([countUp=1])`

#### Description

Returns a group of properties relative to the property on which the expression is written.

For example, if you add the `propertyGroup(1)` expression to the Rotation property of a brush stroke, the expression targets the Transform property group, which contains the Rotation property. If you add `propertyGroup(2)` instead, the expression targets the Brush property group.

This method lets you establish name-independent relationships in the property hierarchy. It is especially useful when duplicating properties that contain expressions.The `numProperties` method for `propertyGroup` returns the number of properties in the property group.

#### Parameters

| Parameter |  Type  |                                      Description                                      |
| --------- | ------ | ------------------------------------------------------------------------------------- |
| `countUp` | Number | Optional. The number of property groups "up" the hierarchy to climb. Defaults to `1`. |

#### Returns

[PropertyGroup object](./propertygroup.md)

#### Example

**Return the number of properties in the group that contains the property on which this expression is written:**

```js
thisProperty.propertyGroup(1).numProperties;
```

---

### smooth()

`thisLayer.position.smooth([width=.2][, samples=5][, t=time])`

#### Description

Smooths the property values over time, converting large, brief deviations in the value to smaller, more evenly distributed deviations. This smoothing is accomplished by applying a box filter to the value of the property at the specified time.

#### Parameters

+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
| Parameter |  Type  |                                                                        Description                                                                        |
+===========+========+===========================================================================================================================================================+
| `width`   | Number | Optional. The range of time (in seconds) over which the filter is averaged. Defaults to `0.2`.                                                            |
+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
| `samples` | Number | Optional. The number of discrete samples evenly spaced over time. Use a larger value for greater smoothness (but decreased performance). Defaults to `5`. |
|           |        |                                                                                                                                                           |
|           |        | Generally, you'll want samples to be an odd number so that the value at the current time is included in the average.                                      |
+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
| `t`       | Number | Optional. The specified time (in comp seconds) to apply the smoothing filter to. Defaults to `time` (the current comp time, in seconds).                  |
+-----------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+

#### Returns

Number or Array

#### Example

**To smooth a position property's animation:**

```js
position.smooth(0.1, 5)
```

---

### speedAtTime()

`thisLayer.position.speedAtTime(t)`

#### Description

Returns the spatial speed value at the specified time.

#### Parameters

| Parameter |  Type  |                         Description                         |
| --------- | ------ | ----------------------------------------------------------- |
| `t`       | Number | The specified time at which to get the spatial speed value. |

#### Returns

Number

---

### temporalWiggle()

`thisLayer.position.temporalWiggle(freq, amp[, octaves=1][, amp_mult=0.5][, t=time])`

#### Description

Samples the property at a wiggled time.

For this function to be meaningful, the property it samples must be animated, because the function alters only the time of sampling, not the value.

#### Parameters

| Parameter  |  Type  |                                      Description                                       |
| ---------- | ------ | -------------------------------------------------------------------------------------- |
| `freq`     | Number | The frequency, in wiggles per second.                                                  |
| `amp`      | Number | The amplitude, in units of the property to which it is applied.                        |
| `octaves`  | Number | Optional. The number of octaves of noise to add together. Defaults to `1`.             |
| `amp_mult` | Number | Optional. The amount that `amp` is multiplied by for each octave. Defaults to `0.5`.   |
| `t`        | Number | Optional. The base start time. Defaults to `time` (the current comp time, in seconds). |

#### Returns

Number or Array

#### Example

**To add a temporal wiggle to scale:**

```js
scale.temporalWiggle(5, 0.2)
```

---

### valueAtTime()

`thisLayer.position.valueAtTime(t)`

#### Description

Returns the value of a property at the specified time, in seconds.

!!! note
    Dan Ebberts provides more examples and techniques for using the `valueAtTime` and `velocityAtTime` methods on [MotionScript](http://www.motionscript.com/mastering-expressions/follow-the-leader.html).

#### Parameters

| Parameter |  Type  |                 Description                 |
| --------- | ------ | ------------------------------------------- |
| `t`       | Number | The time, in seconds, to get the value from |

#### Returns

Number or Array

#### Example

For example, to have a property value for each frame chosen randomly from a set of four values, set your four values as keyframes at `0`, `1`, `2`, and `3` seconds, and then apply the following expression to the property:

```js
valueAtTime(random(4))
```

---

### velocityAtTime()

`thisLayer.position.velocityAtTime(t)`

#### Description

Returns the temporal velocity value at the specified time.

#### Parameters

| Parameter |  Type  |                       Description                       |
| --------- | ------ | ------------------------------------------------------- |
| `t`       | Number | The time, in seconds, to get the temporal velocity from |

#### Returns

Number or Array

---

### wiggle()

`thisLayer.position.wiggle(freq, amp[, octaves=1][, amp_mult=0.5][, t=time])`

#### Description

Randomly shakes (wiggles) the value of the property.

!!! note
    Dan Ebberts provides an example expression and a detailed explanation on his [website](http://www.motionscript.com/design-guide/looping-wiggle.html) that shows how to use the time parameter of the wiggle method to create a looping animation.

#### Parameters

+------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Parameter  |  Type  |                                                                                                               Description                                                                                                               |
+============+========+=========================================================================================================================================================================================================================================+
| `freq`     | Number | Frequency, in wiggles per second.                                                                                                                                                                                                       |
+------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| `amp`      | Number | Amplitude, in units of the property to which it is applied.                                                                                                                                                                             |
+------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| `octaves`  | Number | Optional. Number of octaves of noise to add together. This value controls how much detail is in the wiggle.                                                                                                                             |
|            |        |                                                                                                                                                                                                                                         |
|            |        | Make this value higher than the default to include higher frequencies or lower to include amplitude harmonics in the wiggle. Defaults to `1`.                                                                                           |
+------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| `amp_mult` | Number | Optional. Amount that `amp` is multiplied by for each octave. This value controls how fast the harmonics drop off.                                                                                                                      |
|            |        |                                                                                                                                                                                                                                         |
|            |        | Make this value closer to `1` to have the harmonics added at the same amplitude as the base frequency, or closer to `0` to add in less detail. Defaults to `0.5`.                                                                       |
+------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| `t`        | Number | Optional. Base start time. This value defaults to the current time. Use this parameter if you want the output to be a wiggle of the property value sampled at a different time. Defaults to `time` (the current comp time, in seconds). |
+------------+--------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#### Returns

Number or Array

#### Example

This produces about `5` wiggles per second with an average size of about 20 pixels. In addition to the main wiggle, two more levels of detailed wiggles occur with a frequency of `10` and `20` wiggles per second, and sizes of `10` and `5` pixels, respectively:

```js
position.wiggle(5, 20, 3, 0.5);
```

This example, on a two-dimensional property such as Scale, wiggles both dimensions by the same amount:

```js
const v = wiggle(5, 10);

[v[0], v[0]];
```

This example, on a two-dimensional property, wiggles only along the y-axis:

```js
const freq = 3;
const amp = 50;
const w = wiggle(freq,amp);

[value[0], w[1]];
```

---

## Loop Types

The following loop types are predefined strings used in the "type" parameter for:

- [loopIn()](#loopin)
- [loopInDuration()](#loopinduration)
- [loopOut()](#loopout)
- [loopOutDuration()](#loopoutduration)

+--------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----+
|     Type     |                                                                                                                       Behaviour                                                                                                                       |     |
+==============+=======================================================================================================================================================================================================================================================+=====+
| `"cycle"`    | Default. Repeats the specified segment.                                                                                                                                                                                                               |     |
+--------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----+
| `"pingpong"` | Repeats the specified segment, alternating between forward and backward.                                                                                                                                                                              |     |
+--------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----+
| `"offset"`   | Repeats the specified segment, but offsets each cycle by the difference in the value of the property at the start and end of the segment, multiplied by the number of times the segment has looped.                                                   |     |
+--------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----+
| `"continue"` | Does not repeat the specified segment, but continues to animate a property based on the velocity at the first or last keyframe.                                                                                                                       |     |
|              |                                                                                                                                                                                                                                                       |     |
|              | For example, if the last keyframe of a Scale property of a layer is `100%`, the layer continues to scale from `100%` to the Out point, instead of looping directly back to the Out point. This type does not accept a keyframes or duration argument. |     |
+--------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----+
