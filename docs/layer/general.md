# Layer General

`thisLayer`

!!! info
    On this page, we're going to use `thisLayer` as a sample on how to call these items, however note that any method that returns a [Layer](./layer.md) will work.

---

## Attributes

### Layer.active

`thisLayer.active`

#### Description

Returns `true` if the Video switch is on for the layer and the current time is in the range from the In point of the layer to the Out point of the layer; `false` otherwise.

#### Type

Boolean

---

### Layer.audioActive

`thisLayer.audioActive`

#### Description

Returns `true` if the Audio switch is on for the layer and the current time is in the range from the In point of the layer to the Out point of the layer; `false` otherwise.

#### Type

Boolean

---

### Layer.enabled

`thisLayer.enabled`

#### Description

Whether the layer is enabled.

#### Type

Boolean. `true` if the Video switch is on for the layer; `false` otherwise.

---

### Layer.hasAudio

`thisLayer.hasAudio`

#### Description

Whether the layer has audio.

#### Type

Boolean. `true` if the layer has audio or `false` if it doesn't.

---

### Layer.hasParent

`thisLayer.hasParent`

#### Description

Use the `hasParent` attribute to determine if a layer has a parent layer. You can use this attribute even if the layer has no parent layer at present.

#### Type

Boolean. `true` if the layer has a parent, `false` if it doesn't.

#### Example

The following expression indicates that the layer to which you apply it wiggles based on the position of the parent. If the layer has no parent, then it wiggles based on its own position.

If the layer is given a parent later, then the behavior of the layer changes accordingly:

```js
idx = index;
if (hasParent) {
        idx = parent.index;
}
thisComp.layer(idx).position.wiggle(5,20)
```

---

### Layer.hasVideo

`thisLayer.hasVideo`

#### Description

Whether the layer has video.

#### Type

Boolean. `true` if the layer has audio or `false` if it doesn't.

---

### Layer.height

`thisLayer.height`

#### Description

Returns the height of the layer, in pixels.

If the layer has a [source](./sub-objects.md#layersource), this is the same as either the source [comp height](../objects/comp.md#compheight) or the source [footage height](../objects/footage.md#footageheight) (as applicable).

#### Type

Number

---

### Layer.index

`thisLayer.index`

#### Description

Returns the index number of the layer in the composition.

#### Type

Number

---

### Layer.inPoint

`thisLayer.inPoint`

#### Description

Returns the In point of the layer, in seconds.

!!! note
    In general, the value of outPoint is greater than the value of inPoint. However, if a layer is reversed in time, the value of inPoint is greater than the value of outPoint. Similarly, the value of startTime can be greater than the value of inPoint.

#### Type

Number

---

### Layer.outPoint

`thisLayer.outPoint`

#### Description

Returns the Out point of the layer, in seconds.

#### Type

Number

---

### Layer.parent

`thisLayer.parent`

#### Description

Returns the parent Layer object of the layer, if it has one.

You can check whether a layer has a parent with the [`Layer.hasParent`](#layerhasparent) attribute.

#### Type

[Layer](../layer/layer.md), [Light](../objects/light.md), or [Camera](../objects/camera.md) object

#### Example

```js
position[0] + parent.width
```

---

### Layer.startTime

`thisLayer.startTime`

#### Description

Returns the start time of the layer, in seconds.

#### Type

Number

---

### Layer.width

`thisLayer.width`

#### Description

Returns the width of the layer, in pixels.

If the layer has a [source](./sub-objects.md#layersource), this is the same as either the source [comp width](../objects/comp.md#compwidth) or the source [footage width](../objects/footage.md#footagewidth) (as applicable).

#### Type

Number

---

## Methods

### Layer.sampleImage()

`thisLayer.sampleImage(point[, radius=[0.5, 0.5]][, postEffect=true][, t=time])`

#### Description

Samples the color and alpha channel values of a layer and returns the average alpha-weighted value of the pixels within the specified distance of the point as an array: `[red, green, blue, alpha]`.

!!! note
    Using `sampleImage()` in an expression no longer disables multiprocessing.

#### Parameters

|  Parameter   |            Type            |                                                                                                   Description                                                                                                   |
| ------------ | -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `point`      | 2-dimensional Number array | Required. The point at which to sample, im layer space. The point `[0, 0]` is the center of the upper-left pixel in the layer.                                                                                  |
| `radius`     | 2-dimensional Number array | Optional. Specifies the horizontal and vertical distance from the sample center to the edges of the sampled rectangle. The default value samples one pixel. Defaults to `[0.5, 0.5]`.                           |
| `postEffect` | Boolean                    | Optional. If `true`, to sample the values *after* layer masks and effects **directly applied to the layer** have been rendered. If `false`, sample values *before* layer masks and effects. Defaults to `true`. |
| `t`          | Number                     | Optional. Defaults to `time`.                                                                                                                                                                                   |


#### Type

Array (4-dimensional)

#### Examples

This samples a rectangle 4 pixels wide and 3 pixels high, centered around a point 100 pixels down and to the right of the upper-left corner of the layer:

```js
thisComp.layer(1).sampleImage([100, 100], [2, 1.5])
```
