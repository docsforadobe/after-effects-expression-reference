# Property

**Example:**
Animating with the propertyGroup method and propertyIndex attribute

[image]

In this example, the propertyGroup method for each brush stroke targets the Brush property group because that group is two property groups up from the Rotation property. The propertyIndex attribute in each Brush stroke then returns a unique value for each Brush stroke. The resulting value is then multiplied by the `time` and `200` and applied to each rotation value, rotating each brush stroke differently, creating swirling paint strokes:

```default
propertyGroup(2).propertyIndex * time * 200
propertyGroup(2).propertyIndex * time * 200
```

[image]

---

## value

**Description**

Returns the value of a property at the current time.

**Type**

Number, Array, or String

---

## valueAtTime(`t`)

**Description**

Returns the value of a property at the specified time, in seconds.

For example, to have a property value for each frame chosen randomly from a set of four values, set your four values as keyframes at `0`, `1`, `2`, and `3` seconds, and then apply the following expression to the property:

```default
valueAtTime(random(4))
```

#### NOTE
Dan Ebberts provides more examples and techniques for using the `valueAtTime` and `velocityAtTime` methods on [MotionScript](http://www.motionscript.com/mastering-expressions/follow-the-leader.html).

**Parameters**

| `t`   | Number   |
|-------|----------|

**Type**

Number or Array

---

## velocity

**Description**

Returns the temporal velocity value at the current time. For spatial properties, such as Position, it returns the tangent vector value. The result is the same dimension as the property.

**Type**

Number or Array

---

## velocityAtTime(`t`)

**Description**

Returns the temporal velocity value at the specified time.

**Parameters**

| `t`   | Number   |
|-------|----------|

**Type**

Number or Array

---

## speed

**Description**

Returns a 1D, positive speed value equal to the speed at which the property is changing at the default time. This element can be used only for spatial properties.

**Type**

Number

---

## speedAtTime(`t`)

**Description**

Returns the spatial speed value at the specified time.

**Parameters**

| `t`   | Number   |
|-------|----------|

**Type**

Number

---

## wiggle(`freq`, `amp`, `octaves=1`, `amp_mult=0.5`, `t=time`)

**Description**

Randomly shakes (wiggles) the value of the property.

`freq` value is the frequency in wiggles per second.

`amp` value is the amplitude in units of the property to which it is applied.

`octaves` is the number of octaves of noise to add together. This value controls how much detail is in the wiggle. Make this value higher than the default of 1 to include higher frequencies or lower to include amplitude harmonics in the wiggle.

`amp_mult` is the amount that amp is multiplied by for each octave. This value controls how fast the harmonics drop off. The default is `0.5`; make it closer to `1` to have the harmonics added at the same amplitude as the base frequency, or closer to `0` to add in less detail.

`t` is the base start time. This value defaults to the current time. Use this parameter if you want the output to be a wiggle of the property value sampled at a different time.

Example:

```default
position.wiggle(5, 20, 3, 0.5)
```

This produces about `5` wiggles per second with an average size of about 20 pixels. In addition to the main wiggle, two more levels of detailed wiggles occur with a frequency of `10` and `20` wiggles per second, and sizes of `10` and `5` pixels, respectively.

This example, on a two-dimensional property such as Scale, wiggles both dimensions by the same amount:

```default
v = wiggle(5, 10);
[v[0], v[0]]
```

This example, on a two-dimensional property, wiggles only along the y-axis:

```default
freq = 3;
amp = 50;
w = wiggle(freq,amp);
[value[0],w[1]];
```

#### NOTE
Dan Ebberts provides an example expression and a detailed explanation on his [website](http://www.motionscript.com/design-guide/looping-wiggle.html) that shows how to use the time parameter of the wiggle method to create a looping animation.

**Parameters**

| `freq`     | Number   |
|------------|----------|
| `amp`      | Number   |
| `octaves`  | Number   |
| `amp_mult` | Number   |
| `t`        | Number   |

**Type**

Number or Array

---

## temporalWiggle(`freq`, `amp`, `octaves=1`, `amp_mult=0.5`, `t=time`)

**Description**

Samples the property at a wiggled time.

`freq` value is the frequency in wiggles per second.

`amp` is the amplitude in units of the property to which it is applied.

`octaves` is the number of octaves of noise to add together.

`amp_mult` is the amount that amp is multiplied by for each octave

`t` is the base start time.

For this function to be meaningful, the property it samples must be animated, because the function alters only the time of sampling, not the value.

Example:

```default
scale.temporalWiggle(5, 0.2)
```

**Parameters**

| `freq`     | Number   |
|------------|----------|
| `amp`      | Number   |
| `octaves`  | Number   |
| `amp_mult` | Number   |
| `t`        | Number   |

**Type**

Number or Array

---

## smooth(`width=.2`, `samples=5`, `t=time`)

**Description**

Smooths the property values over time, converting large, brief deviations in the value to smaller, more evenly distributed deviations. This smoothing is accomplished by applying a box filter to the value of the property at the specified time. The width value is the range of time (in seconds) over which the filter is averaged. The samples value is the number of discrete samples evenly spaced over time; use a larger value for greater smoothness (but decreased performance). Generally, you’ll want samples to be an odd number so that the value at the current time is included in the average.

Example:

```default
position.smooth(0.1, 5)
```

**Parameters**

| `width`   | Number   |
|-----------|----------|
| `samples` | Number   |
| `t`       | Number   |

**Type**

Number or Array

---

## loopIn(`type="cycle"`, `numKeyframes=0`)

**Description**

Loops a segment of time that is measured from the first keyframe on the layer forward toward the Out point of the layer. The loop plays from the In point of the layer. The numKeyframes value determines what segment is looped: The segment looped is the portion of the layer from the first keyframe to the numKeyframes+1 keyframe. For example, loopIn(“cycle”, 3) loops the segment bounded by the first and fourth keyframes. The default value of 0 means that all keyframes loop. You can use keyframe-looping methods to repeat a series of keyframes. You can use these methods on most properties. Exceptions include properties that can’t be expressed by simple numeric values in the Timeline panel, such as the Source Text property, path shape properties, and the Histogram property for the Levels effect. Keyframes or duration values that are too large are clipped to the maximum allowable value. Values that are too small result in a constant loop.

| `type`   | result                                                                                                                                                                                                                                                                                                                                                                                |
|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| cycle    | (default) Repeats the specified segment.                                                                                                                                                                                                                                                                                                                                              |
| pingpong | Repeats the specified segment, alternating between forward and backward.                                                                                                                                                                                                                                                                                                              |
| offset   | Repeats the specified segment, but offsets each cycle by the difference in the value of the property at the start and end of the segment, multiplied by the number of times the segment has looped.                                                                                                                                                                                   |
| continue | Does not repeat the specified segment, but continues to animate a property based on the velocity at the first or last keyframe. For example, if the last keyframe of a Scale property of a layer is `100%`, the layer continues to scale from `100%` to the Out point, instead of looping directly back to the Out point. This type does not accept a keyframes or duration argument. |

#### TIP
Use `loopIn("continue") + loopOut("continue") - value` to have a continued motion before and after the property’s keyframes. *Tip from Paul Slemmer.*

**Type**

Number or Array

---

## loopOut(`type="cycle"`, `numKeyframes=0`)

**Description**

Loops a segment of time that is measured from the last keyframe on the layer back toward the In point of the layer. The loop plays until the Out point of the layer. The specified number of keyframes determines the segment to loop. The numKeyframes value sets the number of keyframe segments to loop; the specified range is measured backward from the last keyframe.

For example, `loopOut("cycle", 1)` loops the segment bounded by the last keyframe and second-to-last keyframe. The default value of 0 means that all keyframes loop. See the entry for loopIn for more information.

#### NOTE
David Van Brink provides an instructional article and sample project on his [omino pixel blog](http://omino.com/pixelblog/2007/11/23/salmonella/) that show how to use the Echo effect, the Particle Playground effect, and the `loopOut` method to animate a swarm of stylized swimming bacteria.

**Type**

Number or Array

---

## loopInDuration(`type="cycle"`, `duration=0`)

**Description**

Loops a segment of time that is measured from the first keyframe on the layer forward toward the Out point of the layer. The loop plays from the In point of the layer. Specified duration determines the segment to loop. The duration value sets the number of composition seconds in a segment to loop; the specified range is measured from the first keyframe.

For example, `loopInDuration("cycle", 1)` loops the first second of the entire animation. The default of `0` means that the segment to loop begins at the layer Out point. See the entry for loopIn for more information.

**Type**

Number or Array

---

## loopOutDuration(`type="cycle"`, `duration=0`)

**Description**

Loops a segment of time that is measured from the last keyframe on the layer back toward the In point of the layer. The loop plays until the Out point of the layer. Specified duration determines the segmetn to loop. The duration value sets the number of composition seconds in a segment to loop; the specified range is measured backward from the last keyframe.

For example, `loopOutDuration("cycle", 1)` loops the last second of the entire animation. The default of `0` means that the segment to loop begins at the layer In point. See the entry for loopIn for more information.

**Type**

Number or Array

---

## key(`index`)

**Description**

Returns the Key or MarkerKey object by number.

For example, `key(1)` returns the first keyframe.

**Parameters**

| index   | Number   |
|---------|----------|

**Type**

Key or MarkerKey

---

## key(`markerName`)

**Description**

Returns the MarkerKey object with this name. Use only on marker properties.

| markerName   | String   |
|--------------|----------|

**Type**

MarkerKey

---

## nearestKey(`t`)

**Description**

Returns the Key or MarkerKey object nearest to a designated time `t`.

**Parameters**

| `t`   | Number   |
|-------|----------|

**Type**

Key or MarkerKey

---

## numKeys

**Description**

Returns the number of keyframes on a property. Returns the number of markers on a marker property.

#### NOTE
If you use the Separate Dimensions command to separate the dimensions of the Position property into individual components, the number of keyframes changes, so the value returned by this method changes.

**Type**

Number

---

## propertyGroup(`countUp=1`)

**Description**

Returns a group of properties relative to the property on which the expression is written.

For example, if you add the `propertyGroup(1)` expression to the Rotation property of a brush stroke, the expression targets the Transform property group, which contains the Rotation property. If you add `propertyGroup(2)` instead, the expression targets the Brush property group.

This method lets you establish name-independent relationships in the property hierarchy. It is especially useful when duplicating properties that contain expressions.The `numProperties` method for `propertyGroup` returns the number of properties in the property group.

This example returns the number of properties in the group that contains the property on which the expression is written:

```default
thisProperty.propertyGroup(1).numProperties
```

**Type**

Group

---

## propertyIndex

**Description**

Returns the index of a property relative to other properties in its property group, including property groups within masks, effects, text animators, selectors, shapes, trackers, and track points.

**Type**

Number

---

## name

**Description**

Returns the name of the property or property group.

**Type**

String
