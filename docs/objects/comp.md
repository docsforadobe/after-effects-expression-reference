# Comp

These attributes and methods can be called on Comp objects.

These are typically accessed in a few ways, most commonly:

- `thisComp` to get the Comp object of the active comp the expression is written in,
- `comp("CompName")` to get a specific comp by name,
- `layer("layerName").source`, **if referring to a precomp layer**, to get the targeted precomp layer's source comp

---

## Comp.layer(`index`)

#### Description

Retrieves the layer by number (order in the Timeline panel).

#### Parameters

| Parameter |  Type  |      Description      |
| --------- | ------ | --------------------- |
| `index`   | Number | Index of layer to get |

#### Type

Layer, Light, or Camera object

#### Example

This expression gets the 3rd layer in the current comp:

```js
thisComp.layer(3)
```

---

## Comp.layer(`name`)

#### Description

Retrieves the layer by name. Names are matched according to layer name, or source name if there is no layer name.

If duplicate names exist, After Effects uses the first (topmost) one in the Timeline panel.

#### Parameters

| Parameter |  Type  |     Description      |
| --------- | ------ | -------------------- |
| `name`    | String | Name of layer to get |

#### Type

Layer, Light, or Camera object

#### Example

This expression gets the layer named "Solid 1" from the current comp:

```js
thisComp.layer("Solid 1")
```

---

## Comp.layer(`otherLayer`, `relIndex`)

#### Description

Retrieves the layer that is relIndex layers above or below otherLayer. For example, `thisComp.layer(thisLayer, 1).active` returns true if the next layer down in the Timeline panel is active.

#### Parameters

|  Parameter   |     Type     | Description |
| ------------ | ------------ | ----------- |
| `otherLayer` | Layer Object |             |
| `relIndex`   | Number       |             |

#### Type

Layer, Light, or Camera object

---

## Comp.layerByComment(`comment`)

#### Description

Retrieves a layer by matching the comment parameter to the value in the layer's Comment column.

The matches are simple text matches. They will match partial words, and are case sensitive. Matching does not appear to use regular expressions or wildcards. If duplicate comments exist, After Effects uses the first (topmost) one in the Timeline panel.

#### Parameters

| Parameter |  Type  |           Description            |
| --------- | ------ | -------------------------------- |
| `comment` | String | The comment to find a layer from |

#### Type

Layer, Light, or Camera object

#### Example

```js
thisComp.layerByComment("Control") //note this will match a layer with a comment "Controller" or "Motion Control"
```

---

## Comp.marker

#### Description

!!! note
    You cannot access a composition marker by marker number.

    If you have a project created in a previous version of After Effects that uses composition marker numbers in expressions, you must change those calls to use `marker.key(name)` instead. Because the default name of a composition marker is a number, converting the reference to use the name is often just a matter of surrounding the number with quotation marks.

#### Type

MarkerProperty

---

## Comp.marker.key(`index`)

#### Description

Returns the MarkerKey object of the marker with the specified index. The index refers to the order of the marker in composition time, not to the name of the marker.

#### Parameters

| Parameter |  Type  |       Description       |
| --------- | ------ | ----------------------- |
| `index`   | Number | The marker index to get |

#### Type

MarkerKey

#### Example

This returns the time of the first composition marker:

```js
thisComp.marker.key(1).time
```

---

## Comp.marker.key(`name`)

#### Description

Returns the MarkerKey object of the marker with the specified name. The name value is the name of the marker, as typed in the comment field in the marker dialog box, for example, marker.key("1"). For a composition marker, the default name is a number. If more than one marker in the composition has the same name, this method returns the marker that occurs first in time (in composition time). The value for a marker key is a String, not a Number.

#### Parameters

| Parameter |  Type  |      Description       |
| --------- | ------ | ---------------------- |
| `name`    | String | The marker name to get |

#### Type

MarkerKey

#### Example

This returns the time of the composition marker with the name "0":

```js
thisComp.marker.key("0").time
```

---

## Comp.marker.nearestKey(`time`)

#### Description

Returns the marker that is nearest in comp time to the provided time.

#### Parameters

| Parameter |  Type  |               Description                |
| --------- | ------ | ---------------------------------------- |
| `time`    | Number | The time to find the nearest marker from |

#### Type

MarkerKey

#### Example

This returns the time of the composition marker nearest to the time of 1 second:

```js
thisComp.marker.nearestKey(1).time
```

This expression returns the time of the composition marker nearest to the current time:

```js
thisComp.marker.nearestKey(time).time
```

---

## Comp.marker.numKeys

#### Description

Returns the total number of composition markers in the composition.

#### Type

Number

---

## Comp.numLayers

#### Description

Returns the number of layers in the composition.

#### Type

Number

---

## Comp.activeCamera

#### Description

Returns the Camera object for the camera through which the composition is rendered at the current frame. This camera is not necessarily the camera through which you are looking in the Composition panel.

#### Type

Camera

---

## Comp.width

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

## Comp.height

#### Description

Returns the composition height, in pixels.

#### Type

Number

---

## Comp.duration

#### Description

Returns the composition duration, in seconds.

#### Type

Number

---

## Comp.ntscDropFrame

#### Description

Returns true if the timecode is in drop-frame format.

!!! note
    This functionality was added in After Effects CS5.5

#### Type

Boolean

---

## Comp.displayStartTime

#### Description

Returns the composition start time, in seconds.

#### Type

Number

---

## Comp.frameDuration

#### Description

Returns the duration of a frame, in seconds.

#### Type

Number

---

## Comp.shutterAngle

#### Description

Returns the shutter-angle value of the composition, in degrees.

#### Type

Number

---

## Comp.shutterPhase

#### Description

Returns the shutter phase of the composition, in degrees.

#### Type

Number

---

## Comp.bgColor

#### Description

Returns the background color of the composition.

#### Type

Array (4-dimensional)

---

## Comp.pixelAspect

#### Description

Returns the pixel aspect ratio of the composition.

#### Type

Number

---

## Comp.name

#### Description

Returns the name of the composition.

#### Type

String
