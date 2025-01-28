# Camera

`thisLayer.cameraOption`

This category is for items specific to Camera Layers.

!!! info
    Camera is a subclass of the [Layer object](../layer/layer.md). All methods and attributes of Layer are available when working with Camera, except:

    - `source`
    - `effect`
    - `mask`
    - `width`
    - `height`
    - `anchorPoint`
    - `scale`
    - `opacity`
    - `audioLevels`
    - `timeRemap`
    - all the 3d material properties

---

## Attributes

### Camera.active

`thisLayer.cameraOption.active`

#### Description

Returns `true` if:

1. The camera is the active camera for the composition at the current time: the *video switch* for the camera layer is on,
2. the current time is in the range from the *in point* of the camera layer to the *out point* of the camera layer, **and**
3. The camera is the first (topmost) such camera layer listed in the *timeline panel*

Returns `false` otherwise.

#### Type

Boolean

---

### Camera.aperture

`thisLayer.cameraOption.aperture`

#### Description

Returns the aperture value of a camera, in pixels.

#### Type

Number

---

### Camera.blurLevel

`thisLayer.cameraOption.blurLevel`

#### Description

Returns the blur level value of a camera as a percentage.

#### Type

Number

---

### Camera.depthOfField

`thisLayer.cameraOption.depthOfField`

#### Description

Returns `1` if the Depth Of Field property of a camera is on, or returns `0` if the Depth Of Field property is off.

#### Type

Boolean Number

---

### Camera.focusDistance

`thisLayer.cameraOption.focusDistance`

#### Description

Returns the focus distance value of a camera, in pixels.

#### Type

Number

---

### Camera.highlightGain

`thisLayer.cameraOption.highlightGain`

#### Description

Returns the camera highlight gain, from 1 to 100.

#### Type

Number

---

### Camera.highlightSaturation

`thisLayer.cameraOption.highlightSaturation`

#### Description

Returns the camera highlight saturation, from `1` to `100`.

#### Type

Number

---

### Camera.highlightThreshold

`thisLayer.cameraOption.highlightThreshold`

#### Description

Returns the camera highlight threshhold.

- In an 8-bit comp, this value ranges from `0` to `100`
- In a 16-bit comp, this value ranges from `0` to `32768`
- In a 32-bit comp, this value ranges from `0` to `1.0`

#### Type

Number

---

### Camera.irisAspectRatio

`thisLayer.cameraOption.irisAspectRatio`

#### Description

Returns the camera iris aspect ratio, from 1 to 100.

#### Type

Number

---

### Camera.irisDiffractionFringe

`thisLayer.cameraOption.irisDiffractionFringe`

#### Description

Returns the camera iris diffraction fringe, from 1 to 100.

#### Type

Number

---

### Camera.irisRotation

`thisLayer.cameraOption.irisRotation`

#### Description

Returns the iris rotation value, in degrees.

#### Type

Number

---

### Camera.irisRoundness

`thisLayer.cameraOption.irisRoundness`

#### Description

Returns the camera iris roundness value as a percentage.

#### Type

Number

---

### Camera.irisShape

`thisLayer.cameraOption.irisShape`

#### Description

Returns the iris shape value from 1-10, corresponding to the selected dropdown value.

!!! note
    Value `2` is reserved for the divider.

#### Type

Number

---

### Camera.pointOfInterest

`thisLayer.cameraOption.pointOfInterest`

#### Description

Returns the point of interest values of a camera in world space.

#### Type

Array (3 dimensional)

---

### Camera.zoom

`thisLayer.cameraOption.zoom`

#### Description

Returns the zoom values of a camera in pixels.

#### Type

Number

#### Example

Here's an expression for the Scale property of a layer that maintains the relative size of the layer in frame while changing the z position (depth) of a layer or the Zoom value of a camera:

```js
cam = thisComp.activeCamera;
distance = length(sub(position, cam.position));
scale * distance / cam.zoom;
```
