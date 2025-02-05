# Effect

`thisLayer.effect("Bulge")`

This category contains information relating to Effects.

!!! info
    On this page, we're going to use `thisLayer.effect("Bulge")` as a sample on how to call these items, however note that any method that returns an [Effect](#) will work.

---

## Attributes

### Effect.active

`thisLayer.effect("Bulge").active`

#### Description

Returns `true` if the effect is turned on (the *effect switch* is selected).

#### Type

Boolean

---

## Methods

### Effect.param()

`thisLayer.effect("Bulge").param(name)`

`thisLayer.effect("Bulge").param(index)`

#### Description

Returns a property within an effect. Effect control points are always in layer space.

This method can be called using *either* the property's `name` or its `index`.

#### Parameters

+-----------+--------+-----------------------------------------------+
| Parameter |  Type  |                  Description                  |
+===========+========+===============================================+
| `name`    | String | Property name or index to access property by. |
|           |        |                                               |
| `index`   | Number |                                               |
+-----------+--------+-----------------------------------------------+

#### Returns

[Property object](./property.md)

#### Example

To return the "Bulge Height" property from the "Bulge" effect by name:

```js
thisLayer.effect("Bulge").param("Bulge Height");
```

To return the "Bulge Height" property from the "Bulge" effect by index:

```js
thisLayer.effect("Bulge").param(4);
```
