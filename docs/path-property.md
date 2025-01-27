# Path Property

!!! note
    Available in After Effects CC18 and later.

**Example 1**

Writes the list of point and tangent coordinates from Path 1 of Shape 1 on layer Shape Layer 1, at `time=0`, into a string. Apply this to
the source text property of a text layer for a readout of the coordinates and incoming and outgoing tangents of the shape.

```javascript
pointsList = "";
sampleTime = 0;
myShape = thisComp.layer("Shape Layer 1").content("Shape 1").content("Path 1").path;

for (i = 0; i < myShape.points(sampleTime).length; i++) {
        pointsList += "c: " + myShape.points(sampleTime)[i].toString() + " i: " + myShape.inTangents(sampleTime)[i].toString() + " o: " + myShape.outTangents(sampleTime)[i].toString() + "\n";
}

pointsList;
```

**Example 2**

Reads the coordinates of the first vertex of Mask 1 on Dark Gray Solid 1 and converts them to composition coordinates. Apply this to a 2D point control of an effect, such as Write-on or CC Particle Systems II, to make the effect trace or track the first point of an animated mask. Duplicate the effect and change the path points index value ([0]) to trace or track the other points of the mask.

```javascript
myLayer = thisComp.layer("Dark Gray Solid 1");
myLayer.toComp(myLayer.mask("Mask 1").maskPath.points()[0]);
```

---

## name

**Description**

Returns the name of the property.

**Type**

String

---

## PathProperty.points(`t=time`)

**Description**

Get the x,y coordinates of all points on a path. Coordinates for layer mask path points are relative to the layer’s origin in its upper-left hand corner. Coordinates for Bezier shape path points are are relative to the anchor point of the path’s shape group (ex., “Transform: Shape 1 > Anchor Point”). Coordinates for brush stroke path points are relative to the start of the stroke; the first point is `[0,0]`. This method can be passed into the `createPath()` method for the points parameter when duplicating a path.

Optionally specify the time at which sample to the path.

**Parameters**

| `t`   | Number   |
|-------|----------|

**Type**

Array of number pair arrays, rounded to the fourth decimal place

---

## PathProperty.inTangents(`t=time`)

**Description**

Get the x,y coordinates of the incoming tangent handle for all points on a path. Tangent coordinate values are offset relative to the parent point’s coordinates. i.e., The value [0,0] creates no curvature at the incoming tangent. This method can be passed into the createPath() method for the inTangents parameter when duplicating a path.

Optionally specify the time at which sample to the path.

**Type**

Array of number pair arrays, rounded to the fourth decimal place

---

## PathProperty.outTangents(`t=time`)

**Description**

Get the x, y coordinates of the outgoing tangent handle for all points on a path. Tangent coordinate values are offset relative to the parent point’s coordinates. i.e., The value `[0,0]` creates no curvature at the outgoing tangent. This method can be passed into the createPath() method for the outTangents parameter when duplicating a path.

Optionally specify the time at which sample to the path.

**Parameters**

| `t`   | Number   |
|-------|----------|

**Type**

Array of number pair arrays, rounded to the fourth decimal place

---

## PathProperty.isClosed()

**Description**

Determines if the path is open or closed. Returns `true` if the path is closed, `false` if the path is open. This method can be passed into the `createPath()` method for the `is_closed` parameter when duplicating a path.

**Type**

Boolean

---

## PathProperty.pointOnPath(`percentage=0.5`, `t=time`)

**Description**

Get the x, y coordinates of an arbitrary point along a path. The point is expressed as a percentage of the arc-length of the path. 0% is the first point and 100% is the last point. When the path is closed, 0%
and 100% will return the same coordinates. Percentage of arc-length is used to ensure uniform speed along the path. Other than 0% and 100%, percentages do not necessarily correlate with
the Bezier points on the path. (i.e., For a path with three points, the second point will not necessarily be at 50%.) This also means that for an open path and closed path with identical points, the percentage along the open path will not return the same coordinates as the closed path due to the additional length of the closed path.

Optionally specify the time at which sample to the path.

**Parameters**

| `percentage`   | Number   |
|----------------|----------|
| `t`            | Number   |

**Type**

A number pair array

---

## PathProperty.tangentOnPath(`percentage=0.5`, `t=time`)

**Description**

Get the calculated x,y coordinates of the outgoing tangent handle for an arbitrary point along a path. Tangent coordinate values are offset relative to the parent point’s coordinates. i.e., The value [0,0] creates no curvature at the outgoing tangent. The incoming tangent handle is the inverse of this value (multiply the x,y coordinates by -1).  The tangent’s parent point is expressed as a percentage of the arc-length of the path. Read the description of the pointOnPath() method for details about arc-length percentage. The coordinates returned by tangentOnPath() are calcuated from it’s parent point and will differ from those returned by `outTangents()` if a
user-defined point also exists at that arc-length pecentage. The linear distance between the parent point’s coordinates and `tangentOnPath()` coordinates will always be 1. You can multiply the returned coordinates to create a longer tangent, for example `(myPath.tangentOnPath() * 100)`.

Optionally specify the time at which sample to the path.

**Parameters**

| `percentage`   | Number   |
|----------------|----------|
| `t`            | Number   |

**Type**

A number pair array

---

## PathProperty.normalOnPath(`percentage=0.5`, `t=time`)

**Description**

Get the calculated x,y coordinates of the normal for an arbitrary point along a path. Coordinate values of normals are offset relative to the parent point’s coordinates. i.e., The value `[0,0]` is the same as the parent point. The normal’s parent point is expressed as a percentage of the arc-length of the path. Read the description of the `pointOnPath()` method for
details about arc-length percentage. The coordinates returned by `normalOnPath()` are calcuated from its parent point. The linear distance between the parent point’s coordinates and `normalOnPath()` coordinates will always be `1`. You can multiply the returned coordinates to create a longer normal, for example. `(myPath.normalOnPath() * 100)`.

Optionally specify the time at which sample to the path.

**Parameters**

| `percentage`   | Number   |
|----------------|----------|
| `t`            | Number   |

**Type**

A number pair array

---

## PathProperty.createPath(`points=[[0,0], [100,0], [100,100], [0,100]]`, `inTangents=[]`, `outTangents=[]`, `is_closed=true`)

**Description**

Creates a path object from a set of points and tangents.
The points are defined by an array of number pair arrays representing their `x`, `y` coordinates. The array length must be at least `1`, and can be of
any greater length. The incoming and outgoing tangent handles of the points are defined by an array of number pair arrays representing their x, y offset coordinates. The length of the tangent arrays must be exactly the same as the points parameter. Tangent coordinate values are offset relative to the parent point’s coordinates. i.e., The value `[0,0]` creates no curvature at the incoming tangent. The `points()`, `inTangents()`, `outTangents()`, and `isClosed()` methods of a path can be passed into the `points`, `inTangents`, `outTangents`, and `is_closed` parameters to duplicate a path. The points and tangents of the same path can be passed into `createPath()` with modifications to generate a different result.

For example, the following expression will remove curves from Mask 1 by not passing the inTangents or outTangents parameters:

```default
myMask = mask("Mask 1").path;
myMask.createPath(myMask.points());
```

The following example passes the points and tangents of Mask 1 and converts it to an open path by setting `is_closed` to false:

```default
myMask = mask("Mask 1").path;
myMask.createPath(myMask.points(), myMask.inTangents(), myMask.outTangents(), false);
```

**Parameters**

| `points`      | Array   |
|---------------|---------|
| `inTangents`  | Array   |
| `outTangents` | Array   |
| `is_closed`   | Boolean |

**Type**

Path
