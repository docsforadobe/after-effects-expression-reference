# Comp

`thisComp`
<br/>
`comp("CompName")`
<br/>
`layer("layerName").source`

These attributes and methods can be called on Comp objects.

These are typically accessed in a few ways, most commonly:

- `thisComp` to get the Comp object of the active comp the expression is written in,
- `comp("CompName")` to get a specific comp by name,
- `layer("layerName").source`, **if referring to a precomp layer**, to get the targeted precomp layer's source comp

!!! info
    On this page, we're going to use `thisComp` as a sample on how to call these items, however note that any method that returns a [Comp](#) will work.

---

## Attributes

### Comp.activeCamera

#### Description

Returns the [Camera object](./camera.md) for the camera through which the composition is rendered at the current frame.

This camera is not necessarily the camera through which you are looking in the Composition panel.

#### Type

[Camera](./camera.md)

---

### Comp.bgColor

#### Description

Returns the background color of the composition.

#### Type

Array (4-dimensional)

---

### Comp.displayStartTime

#### Description

Returns the composition start time, in seconds.

#### Type

Number

---

### Comp.duration

#### Description

Returns the composition duration, in seconds.

#### Type

Number

---

### Comp.frameDuration

#### Description

Returns the duration of a frame, in seconds.

#### Type

Number

---

### Comp.height

#### Description

Returns the composition height, in pixels.

#### Type

Number

---

### Comp.marker

#### Description

Returns a given composition's Marker property.

!!! note
    You can no longer access a composition marker by marker number.

    If you have a project created in a previous version of After Effects that uses composition marker numbers in expressions, you must change those calls to use `marker.key(name)` instead. Because the default name of a composition marker is a number, converting the reference to use the name is often just a matter of surrounding the number with quotation marks.

#### Type

[Marker Property](./marker-property.md)

---

### Comp.name

#### Description

Returns the name of the composition.

#### Type

String

---

### Comp.ntscDropFrame

!!! note
    This functionality was added in After Effects CS5.5

#### Description

Returns `true` if the timecode is in drop-frame format.

#### Type

Boolean

---

### Comp.numLayers

#### Description

Returns the number of layers in the composition.

#### Type

Number

---

### Comp.pixelAspect

#### Description

Returns the pixel aspect ratio of the composition.

#### Type

Number

---

### Comp.shutterAngle

#### Description

Returns the shutter-angle value of the composition, in degrees.

#### Type

Number

---

### Comp.shutterPhase

#### Description

Returns the shutter phase of the composition, in degrees.

#### Type

Number

---

### Comp.width

#### Description

Returns the composition width, in pixels.

#### Type

Number

#### Example

Apply the following expression to the Position property of a layer to center the layer in the composition frame:

```js
[thisComp.width / 2, thisComp.height / 2];
```

---

## Methods

### Comp.layer()

`thisComp.layer(index)`
<br/>
`thisComp.layer(name)`
<br/>
`thisComp.layer(otherLayer, relIndex)`

#### Description

Return the [Layer](../layer/layer.md) object with the specified `index` or `name`.

The `index` value refers to the layer order in the Timeline panel.

The `name` value refers to the user-specified layer name, or the layer source name if there is no layer name.

If duplicate names exist, After Effects uses the first (topmost) one in the Timeline panel.

If using the `otherLayer, relIndex` call, this retrieves the layer that is `relIndex` layers above or below `otherLayer`.

#### Parameters

|     Parameter      |            Type            |                         Description                          |
| ------------------ | -------------------------- | ------------------------------------------------------------ |
| `index`<br/>`name` | Number<br/>String          | Layer name or index to get.                                  |
| `otherLayer`       | [Layer](../layer/layer.md) | The "other" layer to start getting layers relative to        |
| `relIndex`         | Number                     | The number of layers to move above or below the `otherLayer` |

#### Returns

[Layer](../layer/layer.md), [Light](./light.md), or [Camera](./camera.md) object

#### Example

Get the 3rd layer in the current comp:

```js
thisComp.layer(3)
```

Get the layer named "Solid 1" from the current comp:

```js
thisComp.layer("Solid 1")
```

Check whether the next layer down in the Timeline panel is active:

```js
const nextLayer = thisComp.layer(thisLayer, 1);
nextLayer.active;
```

---

### Comp.layerByComment()

`thisComp.layerByComment(comment)`

#### Description

Retrieves a layer by matching the comment parameter to the value in the layer's Comment column.

The matches are simple text matches. They will match partial words, and are case sensitive. Matching does not appear to use regular expressions or wildcards. If duplicate comments exist, After Effects uses the first (topmost) one in the Timeline panel.

#### Parameters

| Parameter |  Type  |           Description            |
| --------- | ------ | -------------------------------- |
| `comment` | String | The comment to find a layer from |

#### Returns

[Layer](../layer/layer.md), [Light](./light.md), or [Camera](./camera.md) object

#### Example

```js
// note this will match a layer with a comment "Controller" or "Motion Control"
thisComp.layerByComment("Control");
```
