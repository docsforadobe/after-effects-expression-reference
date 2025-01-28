# Layer Properties

`thisLayer`

When you add masks, effects, paint, or text to a layer, After Effects adds new properties to the Timeline panel. There are too many of these properties to list here, so use the pick whip to learn the syntax for referring to them in your expressions.

!!! info
    On this page, we're going to use `thisLayer` as a sample on how to call these items, however note that any method that returns a [Layer](./layer.md) will work.

---

## Attributes

### Layer.anchorPoint

`thisLayer.anchorPoint`

#### Description

Returns the anchor point value of the layer in the coordinate system of the layer (layer space).

#### Type

Array of Numbers (2- or 3-dimensional)

---

### Layer.audioLevels

`thisLayer.audioLevels`

#### Description

Returns the value of the Audio Levels property of the layer, in decibels. This value is a 2D value; the first value represents the left audio channel, and the second value represents the right. The value is not the amplitude of the audio track of the source material. Instead, it is the value of the Audio Levels property, which may be affected by keyframes.

#### Type

Array of Numbers (2-dimensional)

---

### Layer.marker

`thisLayer.marker`

#### Description

Returns a given layer's [Marker](./marker-property.md) property.

#### Type

[Marker Property](./marker-property.md)

---

### Layer.name

`thisLayer.name`

#### Description

Returns the name of the layer.

#### Type

String

---

### Layer.opacity

`thisLayer.opacity`

#### Description

Returns the opacity value for the layer, expressed as a percentage.

#### Type

Number

---

### Layer.position

`thisLayer.position`

#### Description

Returns the position value of the layer, in world space if the layer has no parent. If the layer has a parent, it returns the position value of the layer in the coordinate system of the parent layer (in the layer space of the parent layer).

#### Type

Array of Numbers (2- or 3-dimensional)

---

### Layer.rotation

`thisLayer.rotation`

#### Description

Returns the rotation value of the layer in degrees. For a 3D layer, it returns the z rotation value in degrees.

#### Type

Number

---

### Layer.scale

`thisLayer.scale`

#### Description

Returns the scale value of the layer, expressed as a percentage.

#### Type

Array of Numbers (2- or 3-dimensional)

---

---

### Layer.timeRemap

`thisLayer.timeRemap`

#### Description

Returns the value of the Time Remap property, in seconds, if Time Remap is enabled.

#### Type

Number
