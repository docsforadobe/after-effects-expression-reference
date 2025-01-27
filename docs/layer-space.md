# Layer Space Transforms

**Description**

Use layer space transform methods to transform values from one space to another, such as from layer space to world space. The `from` methods transform values from the named space (composition or world) to the layer space.

The `to` methods transform values from the layer space to the named space (composition or world). Each transform method takes an optional argument to determine the time at which the transform is computed; however, you can almost always use the current (default) time.

Use `Vec` transform methods when transforming a direction vector, such as the difference between two position values.

Use the plain (non-`Vec`) transform methods when transforming a point, such as position.

Composition (comp) and world space are the same for 2D layers. For 3D layers, however, composition space is relative to the active camera, and world space is independent of the camera.

---

## toComp(`point`, `t=time`)

**Description**

Transforms a point from layer space to composition space.

**Parameters**

| `point`   | Array (2- or 3-dimensional)   |
|-----------|-------------------------------|
| `t`       | Number                        |

**Type**

Array (2- or 3-dimensional)

---

## fromComp(`point`, `t=time`)

**Description**

Transforms a point from composition space to layer space. The resulting point in a 3D layer may have a nonzero value even though it is in layer space.

Example:

```default
fromComp(thisComp.layer(2).position)
```

**Parameters**

| `point`   | Array (2- or 3-dimensional)   |
|-----------|-------------------------------|
| `t`       | Number                        |

**Type**

Array (2- or 3-dimensional)

---

## toWorld(`point`, `t=time`)

**Description**

Transforms a point from layer space to view-independent world space.

Example:

```default
toWorld.effect("Bulge")("Bulge Center")
```

..note::
: Dan Ebberts provides an expression on his [MotionScript website](http://www.motionscript.com/design-guide/auto-orient-y-only.html) that uses the `toWorld` method to auto-orient a layer along only one axis. This is useful, for example, for having characters turn from side to side to follow the camera while remaining upright.

..note::
: Rich Young provides a set of expressions on his [AE Portal website](http://aeportal.blogspot.com/2010/02/fly-around-cc-sphered-layer-in-after.html) that use the toWorld method link a camera and light to a layer with the CC Sphere effect.

**Parameters**

| `point`   | Array (2- or 3-dimensional)   |
|-----------|-------------------------------|
| `t`       | Number                        |

**Type**

Array (2- or 3-dimensional)

---

## fromWorld(`point`, `t=time`)

**Description**

Transforms a point from world space to layer space.

Example:

```default
fromWorld(thisComp.layer(2).position)
```

See Expression example: Create a bulge between two layers for an example of how this method can be used.

**Parameters**

| `point`   | Array (2- or 3-dimensional)   |
|-----------|-------------------------------|
| `t`       | Number                        |

**Type**

Array (2- or 3-dimensional)

---

## toCompVec(vec, `t=time`)

**Description**

Transforms a vector from layer space to composition space.

Example:

```default
toCompVec([1,0])
```

**Parameters**

| `vec`   | Array (2- or 3-dimensional)   |
|---------|-------------------------------|
| `t`     | Number                        |

**Type**

Array (2- or 3-dimensional)

---

## fromCompVec(vec, `t=time`)

**Description**

Transforms a vector from composition space to layer space.

Example (2D layer):

```default
dir = sub(position, thisComp.layer(2).position);
fromCompVec(dir)
```

**Parameters**

| `vec`   | Array (2- or 3-dimensional)   |
|---------|-------------------------------|
| `t`     | Number                        |

**Type**

Array (2- or 3-dimensional)

---

## toWorldVec(vec, `t=time`)

**Description**

Transforms a vector from layer space to world space.

Example:

```default
p1 = effect("Eye Bulge 1")("Bulge Center");
p2 = effect("Eye Bulge 2")("Bulge Center");
toWorld(sub(p1, p2))
```

**Parameters**

| `vec`   | Array (2- or 3-dimensional)   |
|---------|-------------------------------|
| `t`     | Number                        |

**Type**

Array (2- or 3-dimensional)

---

## fromWorldVec(`vec`, `t=time`)

**Description**

Transforms a vector from world space to layer space.

Example:

```default
fromWorld(thisComp.layer(2).position)
```

**Parameters**

| `vec`   | Array (2- or 3-dimensional)   |
|---------|-------------------------------|
| `t`     | Number                        |

**Type**

Array (2- or 3-dimensional)

---

## fromCompToSurface(`point`, `t=time`)

**Description**

Projects a point located in composition space to a point on the surface of the layer (zero z-value) at the location where it appears when viewed from the active camera. This method is useful for setting effect control points. Use with 3D layers only.

**Parameters**

| `point`   | Array (2- or 3-dimensional)   |
|-----------|-------------------------------|
| `t`       | Number                        |

**Type**

Array (2-dimensional)
