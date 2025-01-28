# Global

These attributes and methods are global, top-level elements accessible from any expression across your project. They're among the most commonly-used expression elements.

---

## Attributes

### colorDepth

`colorDepth`

#### Description

Type the project color depth value.

For example, `colorDepth` returns `16` when the project color depth is 16 bits per channel.

#### Type

Number

---

### thisComp

`thisComp`

#### Description

Represents the composition containing the expression.

#### Type

[Comp](../objects/comp.md)

---

### thisLayer

`thisLayer`

#### Description

Represents the layer containing the expression.

Because `thisLayer` is the default object, its use is optional.

For example, you can start an expression with `thisLayer.width` or `width` and get the same result.

#### Type

[Layer](../layer/layer.md), [Light](../objects/light.md), or [Camera](../objects/camera.md) object

---

### thisProject

`thisProject`

#### Description

Represents the project which contains the expression.

#### Type

[Project](../objects/project.md)

---

### thisProperty

`thisProperty`

#### Description

Represents the property containing the expression.

For example, if you write an expression on the Rotation property, you can start an expression with `thisProperty` to refer to the Rotation property.

#### Type

[Property](../objects/property.md)

---

### time

`time`

#### Description

Represents the composition time, in seconds, at which the expression is being evaluated.

#### Type

Number

---

### value

`value`

#### Description

Represents the value at the current time for the property containing the expression.

#### Type

A value of the same property type as the property being refrenced.

---

## Methods

### comp()

`comp(name)`

#### Description

Retrieves another composition by name.

#### Parameters

| Parameter |  Type  |            Description             |
| --------- | ------ | ---------------------------------- |
| `name`    | String | The name of the composition to get |

#### Returns

[Comp](../objects/comp.md)

---

### footage()

`footage(name)`

#### Description

Retrieves a footage item by name.

#### Parameters

| Parameter |  Type  |             Description             |
| --------- | ------ | ----------------------------------- |
| `name`    | String | The name of the footage item to get |

#### Returns

[Footage](../objects/footage.md)

---

### posterizeTime()

`posterizeTime(updatesPerSecond)`

#### Description

This expression allows you to set the frame rate for a property to be lower than the frame rate of the composition.

#### Parameters

|     Parameter      |  Type  |                           Description                           |
| ------------------ | ------ | --------------------------------------------------------------- |
| `updatesPerSecond` | Number | The *number of times per second* the expression should evaluate |

#### Returns

Number

#### Example

To change a property to a random value 1 time per second:

```js
posterizeTime(1);

random()
```

To change a 2d property (such as Position or Scale) to a random value 3 times per second:

```js
posterizeTime(3);

const newValue = random(0, 100);
[newValue, newValue];
```

To change a property to a random value within a specified range, every 12 frames:

```js
const holdFrames = 12;
const minValue = 50;
const maxValue = 100;

posterizeTime(1 / framesToTime(holdFrames));

const newValue = random(minValue, maxValue);
newValue;
```
