# Layer Space Transforms

`thisLayer`

Use layer space transform methods to transform values from one space to another, such as from layer space to world space.

Composition (comp) and world space are the same for 2D layers. For 3D layers, however, composition space is relative to the active camera, and world space is independent of the camera.

!!! info
    On this page, we're going to use `thisLayer` as a sample on how to call these items, however note that any method that returns a [Layer](./layer.md) will work.

#### "From" & "To" Methods

The `from` methods transform values from the named space (composition or world) to the layer space.

The `to` methods transform values from the layer space to the named space (composition or world). Each transform method takes an optional argument to determine the time at which the transform is computed; however, you can almost always use the current (default) time.

#### "Vec" Methods

Use `Vec` transform methods when transforming a direction vector, such as the difference between two position values.

Use the plain (non-`Vec`) transform methods when transforming a point, such as position.

---

## Methods

### toComp()

`thisLayer.toComp(point[, t=time])`

#### Description

Transforms a point from layer space to composition space.

#### Parameters

| Parameter |            Type             |                               Description                               |
| --------- | --------------------------- | ----------------------------------------------------------------------- |
| `point`   | Array (2- or 3-dimensional) | The point to convert                                                    |
| `t`       | Number                      | Optional. The time at which to sample the point at. Defaults to `time`. |

#### Type

Array (2- or 3-dimensional)

---

### fromComp()

`thisLayer.fromComp(point[, t=time])`

#### Description

Transforms a point from composition space to layer space. The resulting point in a 3D layer may have a nonzero value even though it is in layer space.

#### Parameters

| Parameter |            Type             |                               Description                               |
| --------- | --------------------------- | ----------------------------------------------------------------------- |
| `point`   | Array (2- or 3-dimensional) | The point to convert                                                    |
| `t`       | Number                      | Optional. The time at which to sample the point at. Defaults to `time`. |

#### Type

Array (2- or 3-dimensional)

#### Example

```js
fromComp(thisComp.layer(2).position)
```

---

### toWorld()

`thisLayer.toWorld(point[, t=time])`

#### Description

Transforms a point from layer space to view-independent world space.

!!! tip
    Dan Ebberts provides an expression on his [MotionScript website](http://www.motionscript.com/design-guide/auto-orient-y-only.html) that uses the `toWorld` method to auto-orient a layer along only one axis. This is useful, for example, for having characters turn from side to side to follow the camera while remaining upright.

!!! tip
    Rich Young provides a set of expressions on his [AE Portal website](http://aeportal.blogspot.com/2010/02/fly-around-cc-sphered-layer-in-after.html) that use the toWorld method link a camera and light to a layer with the CC Sphere effect.

#### Parameters

| Parameter |            Type             |                               Description                               |
| --------- | --------------------------- | ----------------------------------------------------------------------- |
| `point`   | Array (2- or 3-dimensional) | The point to convert                                                    |
| `t`       | Number                      | Optional. The time at which to sample the point at. Defaults to `time`. |

#### Type

Array (2- or 3-dimensional)

#### Example

```js
toWorld.effect("Bulge")("Bulge Center")
```

---

### fromWorld()

`thisLayer.fromWorld(point[, t=time])`

#### Description

Transforms a point from world space to layer space.

#### Parameters

| Parameter |            Type             |                               Description                               |
| --------- | --------------------------- | ----------------------------------------------------------------------- |
| `point`   | Array (2- or 3-dimensional) | The point to convert                                                    |
| `t`       | Number                      | Optional. The time at which to sample the point at. Defaults to `time`. |

#### Type

Array (2- or 3-dimensional)

#### Example

```js
fromWorld(thisComp.layer(2).position)
```

---

### toCompVec()

`thisLayer.toCompVec(vec[, t=time])`

#### Description

Transforms a vector from layer space to composition space.

#### Parameters

| Parameter |            Type             | Description |
| --------- | --------------------------- | ----------- |
| `vec`     | Array (2- or 3-dimensional) |             |
| `t`       | Number                      |             |

#### Type

Array (2- or 3-dimensional)

#### Example

```js
toCompVec([1, 0])
```

---

### fromCompVec()

`thisLayer.fromCompVec(vec[, t=time])`

#### Description

Transforms a vector from composition space to layer space.

#### Parameters

| Parameter |            Type             | Description |
| --------- | --------------------------- | ----------- |
| `vec`     | Array (2- or 3-dimensional) |             |
| `t`       | Number                      |             |

#### Type

Array (2- or 3-dimensional)

#### Example:

For a 2D layer:

```js
const dir = sub(position, thisComp.layer(2).position);
fromCompVec(dir)
```

---

### toWorldVec()

`thisLayer.toWorldVec(vec[, t=time])`

#### Description

Transforms a vector from layer space to world space.

#### Parameters

| Parameter |            Type             | Description |
| --------- | --------------------------- | ----------- |
| `vec`     | Array (2- or 3-dimensional) |             |
| `t`       | Number                      |             |

#### Type

Array (2- or 3-dimensional)

#### Example

Transform two different "Bulge Center" properties from the *layer space* of the layer the effect is applied to, to the *world space* of the comp the layers live in:

```js
const p1 = effect("Eye Bulge 1")("Bulge Center");
const p2 = effect("Eye Bulge 2")("Bulge Center");

toWorld(sub(p1, p2))
```

---

### fromWorldVec()

`thisLayer.fromWorldVec(vec[, t=time])`

#### Description

Transforms a vector from world space to layer space.

#### Parameters

| Parameter |            Type             | Description |
| --------- | --------------------------- | ----------- |
| `vec`     | Array (2- or 3-dimensional) |             |
| `t`       | Number                      |             |

#### Type

Array (2- or 3-dimensional)

#### Example

Convert layer #2's position from world space to *this layer's* space:

```js
fromWorld(thisComp.layer(2).position)
```

---

### fromCompToSurface()

`thisLayer.fromCompToSurface(point[, t=time])`

#### Description

Projects a point located in composition space to a point on the surface of the layer (zero z-value) at the location where it appears when viewed from the active camera. This method is useful for setting effect control points.

!!! note
    Use with 3D layers only.

#### Parameters

| Parameter |            Type             |                               Description                               |
| --------- | --------------------------- | ----------------------------------------------------------------------- |
| `point`   | Array (2- or 3-dimensional) | The point to convert                                                    |
| `t`       | Number                      | Optional. The time at which to sample the point at. Defaults to `time`. |

#### Type

Array (2-dimensional)
