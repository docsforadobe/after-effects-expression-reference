# Layer Properties

#### Description

When you add masks, effects, paint, or text to a layer, After Effects adds new properties to the Timeline panel. There are too many of these properties to list here, so use the pick whip to learn the syntax for referring to them in your expressions.

---

## Layer.anchorPoint

#### Description

Returns the anchor point value of the layer in the coordinate system of the layer (layer space).

#### Type

Array of Numbers (2- or 3-dimensional)

---

## Layer.position

#### Description

Returns the position value of the layer, in world space if the layer has no parent. If the layer has a parent, it returns the position value of the layer in the coordinate system of the parent layer (in the layer space of the parent layer).

#### Type

Array of Numbers (2- or 3-dimensional)

---

## Layer.scale

#### Description

Returns the scale value of the layer, expressed as a percentage.

#### Type

Array of Numbers (2- or 3-dimensional)

---

## Layer.rotation

#### Description

Returns the rotation value of the layer in degrees. For a 3D layer, it returns the z rotation value in degrees.

#### Type

Number

---

## Layer.opacity

#### Description

Returns the opacity value for the layer, expressed as a percentage.

#### Type

Number

---

## Layer.audioLevels

#### Description

Returns the value of the Audio Levels property of the layer, in decibels. This value is a 2D value; the first value represents the left audio channel, and the second value represents the right. The value is not the amplitude of the audio track of the source material. Instead, it is the value of the Audio Levels property, which may be affected by keyframes.

#### Type

Array of Numbers (2-dimensional)

---

## Layer.timeRemap

#### Description

Returns the value of the Time Remap property, in seconds, if Time Remap is enabled.

#### Type

Number

---

## Layer.marker.key(`index`)

#### Description

Returns the MarkerKey object of the layer marker with the specified index.

#### Parameters

| `index`   | Number   |
|-----------|----------|

#### Type

MarkerKey

---

## Layer.marker.key(`name`)

#### Description

Returns the MarkerKey object of the layer marker with the specified name. The name value is the name of the marker, as typed in the comment field in the marker dialog box, for example, `marker.key("ch1")`. If more than one marker on the layer has the same name, this method returns the marker that occurs first in time (in layer time). The value for a marker key is a `String`, not a `Number`.

This expression on a property ramps the value of the property from `0` to `100` between two markers identified by name:

```js
m1 = marker.key("Start").time;
m2 = marker.key("End").time;
linear(time, m1, m2, 0, 100);
```

#### Parameters

| `name`   | String   |
|----------|----------|

#### Type

MarkerKey

---

## Layer.marker.nearestKey(`t`)

#### Description

Returns the layer marker that is nearest in time to t.

For example, this expression returns the time of the marker on the layer nearest to the time of `1` second:

```js
marker.nearestKey(1).time
```

This expression returns the time of the marker on the layer nearest to the current time:

```js
marker.nearestKey(time).time
```

#### Parameters

| `t`   | Number   |
|-------|----------|

#### Type

MarkerKey

---

## Layer.marker.numKeys

#### Description

Returns the total number of markers on the layer.

#### Type

Number

---

## Layer.name

#### Description

Returns the name of the layer.

#### Type

String
