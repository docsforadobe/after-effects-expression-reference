# PropertyGroup

`thisLayer("ADBE Effect Parade")`

All properties in the Timeline are organized into groups, which share some attributes of properties like `name` and `propertyIndex`.

Property Groups can have a fixed number of properties (e.g. an individual effect whose properties don't change) or a variable number of properties (e.g. the "Effects" group itself which can have any number of effect within it).

#### Top-level groups in a Layer

- Motion Trackers
- Text
- Contents
- Masks
- Effects
- Transform
- Layer Styles
- Geometry Options
- Material Options
- Audio
- Data
- Essential Properties

#### Nested groups

- Individual effects
- Individual masks
- Shape groups
- Text Animators

!!! info
    On this page, we're going to use `thisLayer("ADBE Effect Parade")` (the "Effects" group) as a sample on how to call these items, however note that any method that returns a [PropertyGroup](#) will work.

---

## Attributes

### PropertyGroup.name

`thisLayer("ADBE Effect Parade").name`

#### Description

Returns the name of the property group.

#### Type

String

---

### PropertyGroup.numProperties

`thisLayer("ADBE Effect Parade").numProperties`

#### Description

Returns the number of properties or groups directly within a group.

!!! note
    This does not include properties nested inside child groups.

#### Type

Number

#### Example

To find the number of effects applied to a layer:

```js
thisLayer("ADBE Effect Parade").numProperties
```

---

### PropertyGroup.propertyIndex

`thisLayer("ADBE Effect Parade").propertyIndex`

#### Description

Returns the index of a property group relative to other properties or groups in its property group.

#### Type

Number

---

## Methods

### PropertyGroup.propertyGroup()

`propertyGroup([countUp=1])`

#### Description

Returns a higher-level property group relative to the property group on which the method is called.

See [`propertyGroup()`](property.md#propertygroup) for additional details.

#### Parameters

| Parameter |  Type  |                                      Description                                      |
| --------- | ------ | ------------------------------------------------------------------------------------- |
| `countUp` | Number | Optional. The number of property groups "up" the hierarchy to climb. Defaults to `1`. |


#### Returns

[PropertyGroup object](#)
