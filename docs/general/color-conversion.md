# Color Conversion

Harry Frank provides a video tutorial on his [graymachine website](http://www.graymachine.com/tutorials/rgb-to-hsl-expressions/) that shows how to use these color conversion methods to change the color of the waves produced by the Radio Waves effect.

---

## rgbToHsl()

`rgbToHsl(rgbaArray)`

#### Description

Converts a color in RGBA space to HSLA space.

The input is an Array of normalized red, green, blue, and alpha channel values, all in the range of `0.0` to `1.0`.

The resulting value is an Array of hue, saturation, lightness, and alpha channel values, also in the range of `0.0` to `1.0`.

#### Parameters

|  Parameter  |               Type               |              Description               |
| ----------- | -------------------------------- | -------------------------------------- |
| `rgbaArray` | Array of numbers (4-dimensional) | RGBA values, in the range `[0.0..1.0]` |

#### Type

HSLA Array (4-dimensional)

#### Example:

```js
rgbToHsl.effect("Change Color")("Color To Change")
```

---

## hslToRgb()

`hslToRgb(hslaArray)`

#### Description

Converts a color in HSLA space to RGBA space.

This conversion is the opposite of the conversion performed by the [rgbToHsl()](#rgbtohsl) method.

#### Parameters

|  Parameter  |               Type               |              Description               |
| ----------- | -------------------------------- | -------------------------------------- |
| `hslaArray` | Array of numbers (4-dimensional) | HSLA values, in the range `[0.0..1.0]` |

#### Type

RGBA Array (4-dimensional)

---

## hexToRgb()

`hexToRgb(hexString)`

!!! note
    This functionality was added in After Effects 16.0.

#### Description

Converts a color in hex triplet space to RGB space, or in hex quartet space to RGBA space.

For hex triplets, the alpha channel defaults to 1.0.

#### Parameters

|  Parameter  |  Type  |                                                                                                                      Description                                                                                                                      |
| ----------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `hexString` | String | Hex triplet (6 digits, no alpha channel) or quartet (8 digits, includes alpha channel) containing only numerals or characters A–F.<br/><br/>Optional leading characters 0x, 0X, or # will be ignored.<br/>Characters beyond 8 digits will be ignored. |

#### Type

Array (4-dimensional)

#### Examples

Any of the following will return `[1.0, 0.0, 1.0, 1.0]`:

- `hexToRgb("FF00FF")`
- `hexToRgb("#FF00FF")`
- `hexToRgb("0xFF00FF")`
- `hexToRgb("0XFF00FFFF")`
    - **Note:** This inputs an 8-digit hex quartet; the last two digits set alpha channel to 1.0.
