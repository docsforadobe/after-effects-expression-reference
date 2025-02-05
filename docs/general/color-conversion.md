# Color Conversion

These methods are all around converting colours from one format to another. Think converting a hex code to RGB, so you can use your client's brand colours in an expression in the project, or converting a value to HSL so you can adjust the lightness or saturation procedurally.

---

## Methods

### rgbToHsl()

`rgbToHsl(rgbaArray)`

#### Description

Converts a color in RGBA space to HSLA space.

The input is an Array of normalized red, green, blue, and alpha channel values, all in the range of `0.0` to `1.0`.

The resulting value is an Array of hue, saturation, lightness, and alpha channel values, also in the range of `0.0` to `1.0`.

#### Parameters

|  Parameter  |               Type               |              Description               |
| ----------- | -------------------------------- | -------------------------------------- |
| `rgbaArray` | Array of numbers (4-dimensional) | RGBA values, in the range `[0.0..1.0]` |

#### Returns

HSLA Array (4-dimensional)

#### Example:

```js
rgbToHsl.effect("Change Color")("Color To Change")
```

---

### hslToRgb()

`hslToRgb(hslaArray)`

#### Description

Converts a color in HSLA space to RGBA space.

This conversion is the opposite of the conversion performed by the [rgbToHsl()](#rgbtohsl) method.

#### Parameters

|  Parameter  |               Type               |              Description               |
| ----------- | -------------------------------- | -------------------------------------- |
| `hslaArray` | Array of numbers (4-dimensional) | HSLA values, in the range `[0.0..1.0]` |

#### Returns

RGBA Array (4-dimensional)

---

### hexToRgb()

`hexToRgb(hexString)`

!!! note
    This functionality was added in After Effects 16.0.

#### Description

Converts a color in hex triplet space to RGB space, or in hex quartet space to RGBA space.

For hex triplets, the alpha channel defaults to 1.0.

#### Parameters

+-------------------------------------------------------------------------------------------------------+--------+------------------------------------------------------------------------------------------------------------------------------------+
|                                               Parameter                                               |  Type  |                                                            Description                                                             |
+=======================================================================================================+========+====================================================================================================================================+
| `hexString`                                                                                           | String | Hex triplet (6 digits, no alpha channel) or quartet (8 digits, includes alpha channel) containing only numerals or characters A–F. |
|                                                                                                       |        |                                                                                                                                    |
| Optional leading characters 0x, 0X, or # will be ignored. Characters beyond 8 digits will be ignored. |        |                                                                                                                                    |
+-------------------------------------------------------------------------------------------------------+--------+------------------------------------------------------------------------------------------------------------------------------------+

#### Returns

Array (4-dimensional)

#### Examples

Any of the following will return `[1.0, 0.0, 1.0, 1.0]`:

- `hexToRgb("FF00FF")`
- `hexToRgb("#FF00FF")`
- `hexToRgb("0xFF00FF")`
- `hexToRgb("0XFF00FFFF")`
    - **Note:** This inputs an 8-digit hex quartet; the last two digits set alpha channel to 1.0.
