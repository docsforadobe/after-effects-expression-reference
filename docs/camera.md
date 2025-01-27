<a id="camera"></a>

# Camera

Camera objects have the same attributes and methods as Layer objects, except for:

* `source`
* `effect`
* `mask`
* `width`
* `height`
* `anchorPoint`
* `scale`
* `opacity`
* `audioLevels`
* `timeRemap`
* all the material properties

---

<a id="camera-pointofinterest"></a>

## Camera.pointOfInterest

**Description**

Returns the point of interest values of a camera in world space.

**Type**

Array (3 dimensional)

---

<a id="camera-zoom"></a>

## Camera.zoom

**Description**

Returns the zoom values of a camera in pixels.

Here’s an expression for the Scale property of a layer that maintains the relative size of the layer in frame while changing the z position (depth) of a layer or the Zoom value of a camera:

```default
cam = thisComp.activeCamera;
distance = length(sub(position, cam.position));
scale * distance / cam.zoom;
```

**Type**

Number

---

<a id="camera-depthoffield"></a>

## Camera.depthOfField

**Description**

Returns `1` if the Depth Of Field property of a camera is on, or returns `0` if the Depth Of Field property is off.

**Type**

Boolean Number

---

<a id="camera-focusdistance"></a>

## Camera.focusDistance

**Description**

Returns the focus distance value of a camera, in pixels.

**Type**

Number

---

<a id="camera-aperture"></a>

## Camera.aperture

**Description**

Returns the aperture value of a camera, in pixels.

**Type**

Number

---

<a id="camera-blurlevel"></a>

## Camera.blurLevel

**Description**

Returns the blur level value of a camera as a percentage.

**Type**

Number

---

<a id="camera-irisshape"></a>

## Camera.irisShape

**Description**

Returns the iris shape value from 1-10, corresponding to the selected dropdown value.

<!-- note: Value ``2`` is reserved for the divider. -->

**Type**

Number

---

<a id="camera-irisrotation"></a>

## Camera.irisRotation

**Description**

Returns the iris rotation value, in degrees.

**Type**

Number

---

<a id="camera-irisroundness"></a>

## Camera.irisRoundness

**Description**

Returns the camera iris roundness value as a percentage.

**Type**

Number

---

<a id="camera-irisaspectratio"></a>

## Camera.irisAspectRatio

**Description**

Returns the camera iris aspect ratio, from 1 to 100.

**Type**

Number

---

<a id="camera-irisdiffractionfringe"></a>

## Camera.irisDiffractionFringe

**Description**

Returns the camera iris diffraction fringe, from 1 to 100.

**Type**

Number

---

<a id="camera-highlightgain"></a>

## Camera.highlightGain

**Description**

Returns the camera highlight gain, from 1 to 100.

**Type**

Number

---

<a id="camera-highlightthreshold"></a>

## Camera.highlightThreshold

**Description**

Returns the camera highlight threshhold.

- In an 8-bit comp, this value ranges from 0 to 100
- In a 16-bit comp, this value ranges from 0 to 32768
- In a 32-bit comp, this value ranges from 0 to 1.0

**Type**

Number

---

<a id="camera-highlightsaturation"></a>

## Camera.highlightSaturation

**Description**

Returns the camera highlight saturation, from 1 to 100.

**Type**

Number

---

<a id="camera-active"></a>

## Camera.active

**Description**

Returns `true` if the camera:

1. is the active camera for the composition at the current time: the *video switch* for the camera layer is on
2. the current time is in the range from the *in point* of the camera layer to the *out point* of the camera layer
3. and it is the first (topmost) such camera layer listed in the *timeline panel*

Returns `false` otherwise.

**Type**

Boolean
