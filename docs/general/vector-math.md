# Vector Math

Vector Math functions are global methods that perform operations on arrays, treating them as mathematical vectors.

Unless otherwise specified, Vector Math methods are lenient about dimensions and return a value that is the dimension of the largest input Array object, filling in missing elements with zeros.

Unlike built-in JavaScript methods, such as `Math.sin`, these methods are not used with the `Math` prefix.

#### Example

This expression returns `[11, 22, 3]`:

```js
add([10, 20], [1, 2, 3])
```

---

## Methods

### add()

`add(vec1, vec2)`

#### Description

Adds two vectors.

#### Parameters

| Parameter | Type  |      Description      |
| --------- | ----- | --------------------- |
| `vec1`    | Array | First vector to add.  |
| `vec2`    | Array | Second vector to add. |

#### Returns

Array

---

### clamp()

`clamp(value, limit1, limit2)`

#### Description

The value of each component of `value` is constrained to fall between the values of the corresponding values of `limit1` and `limit2`.

#### Parameters

| Parameter |      Type       |             Description             |
| --------- | --------------- | ----------------------------------- |
| `value`   | Number or Array | Value to clamp.                     |
| `limit1`  | Number or Array | Minimum amount to clamp `value` to. |
| `limit2`  | Number or Array | Maximum amount to clamp `value` to. |

#### Returns

Number or Array

#### Example

Ensure that a wiggled amount never exceeds the 0-100 range:

```js
const wiggled = wiggle(0.5, 500);
clamp(wiggled, 0, 500);
```

---

### cross()

`cross(vec1, vec2)`

#### Description

Returns the vector cross product of `vec1` and `vec2`.

Refer to a math reference or JavaScript guide for more information.

#### Parameters

| Parameter |            Type             |                 Description                  |
| --------- | --------------------------- | -------------------------------------------- |
| `vec1`    | Array (2- or 3-dimensional) | First vector to calculate cross product of.  |
| `vec2`    | Array (2- or 3-dimensional) | Second vector to calculate cross product of. |

#### Returns

Array (2- or 3-dimensional)

---

### div()

`div(vec, amount)`

#### Description

Divides every element of the vector by the amount.

#### Parameters

| Parameter |  Type  |       Description       |
| --------- | ------ | ----------------------- |
| `vec`     | Array  | The vector to divide    |
| `amount`  | Number | The amount to divide by |

#### Returns

Array

---

### dot()

`dot(vec1, vec2)`

#### Description

Returns the dot (inner) product of the vector arguments.

#### Parameters

| Parameter | Type  |                Description                 |
| --------- | ----- | ------------------------------------------ |
| `vec1`    | Array | First vector to calculate dot product of.  |
| `vec2`    | Array | Second vector to calculate dot product of. |

#### Returns

Number

---

### length()

`length(vec[, point2])`

#### Description

Returns the length of vector `vec`.

If a second argument is provided, instead treats the first argument as a point and returns the distance between the two points.

!!! tip
    Using `length()` with two arguments is the same as `length(sub(vec, point2))`.

#### Parameters

| Parameter | Type  |                         Description                          |
| --------- | ----- | ------------------------------------------------------------ |
| `vec`     | Array | The vector to normalize, or the first point to measure from. |
| `point2`  | Array | Optional. The second point to measure to.                    |

#### Returns

Number

#### Example

For example, add this expression to the Focus Distance property of a camera to lock the focal plane to the camera's point of interest so that the point of interest is in focus:

```js
length(position, pointOfInterest)
```

---

### lookAt()

`lookAt(fromPoint, atPoint)`

#### Description

Orients a layer to look at a given point, from a given point.

The return value can be used as an expression for the Orientation property, making the z-axis of the layer point at atPoint.

This method is especially useful for cameras and lights.

!!! tip
    If you use this expression on a camera, turn off auto-orientation.

#### Parameters

|  Parameter  |         Type          |                        Description                         |
| ----------- | --------------------- | ---------------------------------------------------------- |
| `fromPoint` | Array (3-dimensional) | The location (in world space) of the layer to orient.      |
| `atPoint`   | Array (3-dimensional) | The point (in world space) you want to point the layer at. |

#### Returns

Array (3-dimensional)

#### Example

This expression on the Orientation property of a spot light makes the light point at the anchor point of layer number 1 in the same composition:

```js
lookAt(position, thisComp.layer(1).position)
```

---

### mul()

`mul(vec, amount)`

#### Description

Multiplies every element of the vector by the amount.

#### Parameters

| Parameter |  Type  |        Description        |
| --------- | ------ | ------------------------- |
| `vec`     | Array  | The vector to multiply    |
| `amount`  | Number | The amount to multiply by |

#### Returns

Array

---

### normalize()

`normalize(vec)`

#### Description

Normalizes the vector so that its length is `1.0`.

Using the normalize method is a short way of performing the operation `div(vec, length(vec))`.

#### Parameters

| Parameter | Type  |       Description       |
| --------- | ----- | ----------------------- |
| `vec`     | Array | The vector to normalize |

#### Returns

Array

---

### sub()

`sub(vec1, vec2)`

#### Description

Subtracts two vectors.

#### Parameters

| Parameter | Type  |    Description    |
| --------- | ----- | ----------------- |
| `vec1`    | Array | The first vector  |
| `vec2`    | Array | The second vector |

#### Returns

Array
