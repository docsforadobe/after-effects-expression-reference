# Mask

`mask("Mask 1")`

This category contains information relating to mask objects. To manipulate the actual mask *path*, see [Mask Path](#maskmaskpath).

!!! note
    You can link Mask Path properties to other path properties (paths in a shape layer and brush strokes), but the properties are not accessible for direct numerical manipulation through expressions.

---

## Attributes

### Mask.invert

`mask("Mask 1").invert`

#### Description

Returns `true` if the mask is inverted or `false` if it is not.

#### Type

Boolean

---

### Mask.maskExpansion

`mask("Mask 1").maskExpansion`

#### Description

Returns the expansion value of a mask, in pixels.

#### Type

Number

---

### Mask.maskFeather

`mask("Mask 1").maskFeather`

#### Description

Returns the feather value of a mask, in pixels.

#### Type

Number

---

### Mask.maskOpacity

`mask("Mask 1").maskOpacity`

#### Description

Returns the opacity value of a mask as a percentage.

#### Type

Number

---

### Mask.maskPath

`mask("Mask 1").maskPath`

#### Description

Returns the actual mask [Path](./path-property.md).

#### Type

[Path object](./path-property.md)
