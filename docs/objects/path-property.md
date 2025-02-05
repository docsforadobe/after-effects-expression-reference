# Path Property

`thisLayer.mask("Mask 1").maskPath`

`thisLayer.content("Shape 1").content("Path 1").path;`

!!! note
    This functionality was added in After Effects 15.0 (CC)

This category contains information relating to mask & shape *paths*.

!!! info
    On this page, we're going to use `thisLayer.mask("Mask 1").maskPath` as a sample on how to call these items, however note that any method that returns a [Path](#) will work.

---

## Attributes

### name

`thisLayer.mask("Mask 1").maskPath.name`

#### Description

Returns the name of the property.

#### Type

String

---

## Methods

### PathProperty.createPath()

`thisLayer.mask("Mask 1").maskPath.createPath(points=[[0,0], [100,0], [100,100], [0,100]], inTangents=[], outTangents=[], is_closed=true)`

#### Description

Creates a path object from a set of points and tangents.

The [`points()`](#pathpropertypoints), [`inTangents()`](#pathpropertyintangents), [`outTangents()`](#pathpropertyouttangents), and [`isClosed()`](#pathpropertyisclosed) methods of a path can be passed into the `points`, `inTangents`, `outTangents`, and `is_closed` parameters to duplicate a path.

The points and tangents of the same path can be passed into `createPath()` with modifications to generate a different result.

#### Parameters

|   Parameter   |            Type             |                                                                                                                                                                    Description                                                                                                                                                                    |
| ------------- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `points`      | Array of number pair arrays | Optional. An array of number pair arrays representing the `[x, y]` coordinates of the points. The array must contain at least 1 item, and can be of any greater length. Defaults to `[[0,0], [100,0], [100,100], [0,100]]`.                                                                                                                       |
| `inTangents`  | Array of number pair arrays | Optional. An array of number pair arrays representing their `[x, y]` *offset* coordinates. The length of this array must be exactly the same as the `points` parameter. Defaults to `[]`.<br/><br/>Coordinate values are offset relative to the parent point's coordinates. i.e. The value `[0, 0]` creates no curvature at the incoming tangent. |
| `outTangents` | Array of number pair arrays | Optional. See `inTangents`. Defaults to `[]`.                                                                                                                                                                                                                                                                                                     |
| `is_closed`   | Boolean                     | Optional. Defaults to `true`.                                                                                                                                                                                                                                                                                                                     |

#### Returns

[Path](#)

#### Example

For example, the following expression will remove curves from Mask 1 by not passing the inTangents or outTangents parameters:

```js
const myMask = mask("Mask 1").path;
myMask.createPath(myMask.points());
```

The following example passes the points and tangents of Mask 1 and converts it to an open path by setting `is_closed` to `false`:

```js
const myMask = mask("Mask 1").path;
myMask.createPath(myMask.points(), myMask.inTangents(), myMask.outTangents(), false);
```

---

### PathProperty.inTangents()

`thisLayer.mask("Mask 1").maskPath.inTangents([t=time])`

#### Description

Get the `[x, y]` coordinates of the incoming tangent handle for all points on a path.

Tangent coordinate values are offset relative to the parent point's coordinates (i.e. the value `[0, 0]` creates no curvature at the incoming tangent).

This method can be passed into the [`createPath()`](#pathpropertycreatepath) method for the `inTangents` parameter when duplicating a path.


#### Parameters

| Parameter |  Type  |                                                          Description                                                           |
| --------- | ------ | ------------------------------------------------------------------------------------------------------------------------------ |
| `t`       | Number | Optional. The specified time (in comp seconds) to sample the tangents. Defaults to `time` (the current comp time, in seconds). |

#### Returns

Array of number pair arrays, rounded to the fourth decimal place

---

### PathProperty.isClosed()

`thisLayer.mask("Mask 1").maskPath.isClosed()`

#### Description

Determines if the path is open or closed. Returns `true` if the path is closed, `false` if the path is open.

This method can be passed into the [`createPath()`](#pathpropertycreatepath) method for the `is_closed` parameter when duplicating a path.

#### Returns

Boolean

---

### PathProperty.normalOnPath()

`thisLayer.mask("Mask 1").maskPath.normalOnPath(percentage=0.5, t=time)`

#### Description

Get the calculated `[x, y]` coordinates of the normal for an arbitrary point along a path.

Coordinate values of normals are offset relative to the parent point's coordinates (i.e. the value `[0, 0]` is the same as the parent point).

The normal's parent point is expressed as a percentage of the arc-length of the path. Read the description of the [`pointOnPath()`](#pathpropertypointonpath) method for details about arc-length percentage.

The linear distance between the parent point's coordinates and `normalOnPath()` coordinates will always be `1`.

#### Parameters

|  Parameter   |  Type  |                                                        Description                                                         |
| ------------ | ------ | -------------------------------------------------------------------------------------------------------------------------- |
| `percentage` | Number | Optional. The percentage along the path at which to sample the normal. Defaults to `0.5` (50%).                            |
| `t`          | Number | Optional. The specified time (in comp seconds) to sample the path. Defaults to `time` (the current comp time, in seconds). |

#### Returns

A number pair array

#### Example

**Sample a normal and make it longer:**

```js
myPath.normalOnPath() * 100
```

---

### PathProperty.outTangents()

`thisLayer.mask("Mask 1").maskPath.outTangents([t=time])`

#### Description

Get the `[x, y]` coordinates of the outgoing tangent handle for all points on a path.

Tangent coordinate values are offset relative to the parent point's coordinates (i.e. the value `[0, 0]` creates no curvature at the outgoing tangent).

This method can be passed into the [`createPath()`](#pathpropertycreatepath) method for the `outTangents` parameter when duplicating a path.

#### Parameters

| Parameter |  Type  |                                                          Description                                                           |
| --------- | ------ | ------------------------------------------------------------------------------------------------------------------------------ |
| `t`       | Number | Optional. The specified time (in comp seconds) to sample the tangents. Defaults to `time` (the current comp time, in seconds). |

#### Returns

Array of number pair arrays, rounded to the fourth decimal place

---

### PathProperty.pointOnPath()

`thisLayer.mask("Mask 1").maskPath.pointOnPath([percentage=0.5][, t=time])`

#### Description

Get the `[x, y]` coordinates of an arbitrary point along a path.

The point is expressed as a percentage of the arc-length of the path. `0.0` (0%) is the first point and `1.0` (100%) is the last point. When the path is closed, 0% and 100% will return the same coordinates.

!!! info
    Percentage of arc-length is used to ensure uniform speed along the path.

    Other than 0% and 100%, percentages do not necessarily correlate with the Bezier points on the path. (i.e., For a path with three points, the second point will not necessarily be at 50%.)

    This also means that for an open path and closed path with identical points, the percentage along the open path will not return the same coordinates as the closed path due to the additional length of the closed path.

|  Parameter   |  Type  |                                                        Description                                                         |
| ------------ | ------ | -------------------------------------------------------------------------------------------------------------------------- |
| `percentage` | Number | Optional. The percentage along the path at which to sample the point. Defaults to `0.5` (50%).                             |
| `t`          | Number | Optional. The specified time (in comp seconds) to sample the path. Defaults to `time` (the current comp time, in seconds). |

#### Returns

A number pair array

---

### PathProperty.points()

`thisLayer.mask("Mask 1").maskPath.points([t=time])`

#### Description

Get the x,y coordinates of all points on a path.

The returned values are relative, depending on the context:
- Coordinates for **layer mask path points** are relative to the layer's origin in its upper-left hand corner.
- Coordinates for **Bezier shape path points** are are relative to the anchor point of the path's shape group
    - (ex., "Transform: Shape 1 > Anchor Point").
- Coordinates for **brush stroke path points** are relative to the **start of the stroke**; the first point is `[0,0]`.
    - This method can be passed into the [`createPath()`](#pathpropertycreatepath) method for the points parameter when duplicating a path.

#### Parameters

| Parameter |  Type  |                                                        Description                                                         |
| --------- | ------ | -------------------------------------------------------------------------------------------------------------------------- |
| `t`       | Number | Optional. The specified time (in comp seconds) to sample the path. Defaults to `time` (the current comp time, in seconds). |

#### Returns

Array of number pair arrays, rounded to the fourth decimal place

#### Example

**Read the coordinates of the first vertex of Mask 1 on Dark Gray Solid 1 and converts them to composition coordinates.**

Apply this to a 2D point control of an effect, such as Write-on or CC Particle Systems II, to make the effect trace or track the first point of an animated mask.

Duplicate the effect and change the path points index value ([0]) to trace or track the other points of the mask.

```js
const myLayer = thisComp.layer("Dark Gray Solid 1");
myLayer.toComp(myLayer.mask("Mask 1").maskPath.points()[0]);
```

---

### PathProperty.tangentOnPath()

`thisLayer.mask("Mask 1").maskPath.tangentOnPath([percentage=0.5][, t=time])`

#### Description

Get the calculated `[x, y]` coordinates of the outgoing tangent handle for an arbitrary point along a path.

Tangent coordinate values are offset relative to the parent point's coordinates (i.e. the value [0, 0] creates no curvature at the outgoing tangent). Values will differ from those returned by `outTangents()` if a user-defined point also exists at that arc-length pecentage.

The incoming tangent handle is the inverse of this value (multiply the `[x, y]` coordinates by `-1`).

The tangent's parent point is expressed as a percentage of the arc-length of the path. Read the description of the [`pointOnPath()`](#pathpropertypointonpath) method for details about arc-length percentage.

The linear distance between the parent point's coordinates and `tangentOnPath()` coordinates will always be `1`.

#### Parameters


|  Parameter   |  Type  |                                                        Description                                                         |
| ------------ | ------ | -------------------------------------------------------------------------------------------------------------------------- |
| `percentage` | Number | Optional. The percentage along the path at which to sample the tangent. Defaults to `0.5` (50%).                           |
| `t`          | Number | Optional. The specified time (in comp seconds) to sample the path. Defaults to `time` (the current comp time, in seconds). |

#### Returns

A number pair array

#### Example

**Sample a tangent and make it longer:**

```js
myPath.tangentOnPath() * 100
```

---

## Example

Writes the list of point and tangent coordinates from Path 1 of Shape 1 on layer Shape Layer 1, at `time=0`, into a string.

Apply this to the source text property of a text layer for a readout of the coordinates and incoming and outgoing tangents of the shape.

```js
let pointsList = "";
const sampleTime = 0;
const myShape = thisComp.layer("Shape Layer 1").content("Shape 1").content("Path 1").path;

for (i = 0; i < myShape.points(sampleTime).length; i++) {
    pointsList += "c: " + myShape.points(sampleTime)[i].toString() + " i: " + myShape.inTangents(sampleTime)[i].toString() + " o: " + myShape.outTangents(sampleTime)[i].toString() + "\n";
}

pointsList;
```
