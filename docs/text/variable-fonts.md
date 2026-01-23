# Variable Font Axes

`text.animator("Animator Name").property.fontAxis[Tag]`

!!! note
    This functionality was added in After Effects 26.0.

Variable font axes can be accessed in expressions through Text Animator groups. Each added axis is accessed using the pattern `fontAxis[Tag]` where `Tag` is the **4-character axis tag**. 

The axis tag is a 4-character identifier (e.g., `Wght` for Weight, `Wdth` for Width). See list below for common identifiers.

#### Common Axis Tags

- `fontAxisWght` - Weight
- `fontAxisWdth` - Width
- `fontAxisSlnt` - Slant
- `fontAxisItal` - Italic
- `fontAxisOpsz` - Optical Size

Returns the value of a variable font axis property from a text animator.

!!! note
    Axes must exist on the variable font to have any effect. Fonts may also include custom axes with 4-character uppercase tags.

#### Type

[Property](../objects/property.md) (Number)

---

## Examples

Reference a variable font axis from another property:

```js
text.animator("Animator 1").property.fontAxisWght
```

Link layer opacity to font weight:

```js
const weight = text.animator("Animator 1").property.fontAxisWght;
weight / 10;
```
