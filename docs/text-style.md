# Text Style

Most of these functions are accessible from the [SourceText.style](text-sourcetext.md#sourcetext-style) object in AE 17.0 and later. Where noted, additional methods were added in AE 25.0. The ability to control per-character styling was also added in 25.0. Use the second and third arguments (when available) to control per-character styling.

#### NOTE
When using per-character styling, line breaks and spaces are also considered characters and must be accounted for (or skipped, if desired) when calcuating character indexes.

For more info on working with text styles, see:

- [Use Expressions to Edit and Access Text Properties on helpx.adobe.com](https://helpx.adobe.com/after-effects/user-guide.html/after-effects/using/expressions-text-properties.ug.html)
- [After Effects 2020: Express Yourself (and Your Text) on blog.adobe.com](https://blog.adobe.com/en/publish/2020/01/24/after-effects-2020-express-yourself-and-your-text)

All the methods for [Text Style](#textstyle) will return a [Text Style](#textstyle) object, so you can call them in a chain, e.g.:

```default
text.sourceText.style.setFont("Times New Roman").setFontSize(42).setText("New Text");
```

---

## TextStyle.setText(`value`)

**Description**

This is used when you want to define (or inherit) a [Text Style](#textstyle) while setting the text content separately.

For example, to inherit the style and content from another layer:

```default
const referenceText = thisComp.layer("Source Layer Name").text.sourceText;

const style = referenceText.getStyleAt(0,0);
style.setText(referenceText);
```

Or to create a custom style and then set the text within the expression:

```default
text.sourceText.createStyle().setFontSize(300).setFont("Impact").setText("Hello world!");
```

**Parameters**

| `value`   | String. The text to set.   |
|-----------|----------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.replaceText(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

This is used when you want to define (or inherit) a [Text Style](#textstyle), while setting the content for a substring of the text.

For example, to create a custom style and then set a substring of the text within the expression:

```default
// assume the value of the source text is "Old Text"
const referenceText = thisComp.layer("Source Layer Name").text.sourceText;
const style = referenceText.getStyleAt(0,0);

 // This will change the text from "Old Text" to "NewText" as the first 4 characters are replaced.
style.replaceText("New", 0, 4);
```

**Parameters**

| `value`           | Required. String. The text to set.                                                                                          |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.fontSize

**Description**

Returns the value of Font Size for a Text layer.

**Type**

Number

---

## TextStyle.setFontSize(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Font Size to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Number. The Font Size to set.                                                                                     |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.font

**Description**

Returns the font name for a Text layer.

**Type**

String

---

## TextStyle.setFont(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the font to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. String. The font to set.                                                                                          |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.isFauxBold

**Description**

Returns whether Faux Bold is enabled.

**Type**

Boolean

---

## TextStyle.setFauxBold(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Faux Bold status. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Boolean. Whether to enable or disable Faux Bold.                                                                  |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.isFauxItalic

**Description**

Returns whether Faux Italics are enabled.

**Type**

Boolean

---

## TextStyle.setFauxItalic(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Faux Italics status. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Boolean. Whether to enable or disable Faux Italics.                                                               |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.isAllCaps

**Description**

Returns whether All Caps is enabled.

**Type**

Boolean

---

## TextStyle.setAllCaps(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the All Caps status. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Boolean. Whether to enable or disable All Caps.                                                                   |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.isSmallCaps

**Description**

Returns whether Small Caps is enabled.

**Type**

Boolean

---

## TextStyle.setSmallCaps(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Small Caps status. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Boolean. Whether to enable or disable Small Caps.                                                                 |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.tracking

**Description**

Returns the value of Tracking for a Text layer.

**Type**

Number

---

## TextStyle.setTracking(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Tracking to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Number. The Tracking value to set.                                                                                |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.leading

**Description**

Returns the value of Leading for a Text layer.

**Type**

Number

---

## TextStyle.setLeading(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Leading to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

Keep in mind that [TextStyle.isAutoLeading](#textstyle-isautoleading) must be `false` in order for setLeading() to have any visible affect. You can set Leading to a value other than Auto in the Properties or Character panel, or via [TextStyle.setAutoLeading(value, startIndex, numOfCharacters)](#textstyle-setautoleading).

**Parameters**

| `value`           | Required. Number. The Leading value to set.                                                                                 |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.isAutoLeading

**Description**

Returns whether Auto Leading is enabled.

**Type**

Boolean

---

## TextStyle.setAutoLeading(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Auto Leading status. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Boolean. Whether to enable or disable Auto Leading.                                                               |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.baselineShift

**Description**

Returns the value of Baseline Shift for a Text layer.

**Type**

Number

---

## TextStyle.setBaselineShift(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Baseline Shift to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Number. The Baseline Shift value to set.                                                                          |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.applyFill

**Description**

Returns whether Fill Color is enabled.

**Type**

Boolean

---

## TextStyle.setApplyFill(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set whether Fill Color is enabled. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Boolean. Whether to enable or disable Fill.                                                                       |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.fillColor

**Description**

Returns the text Fill Color as RGB values on a scale from 0 - 1.0.

**Type**

Array of Numbers.

---

## TextStyle.setFillColor(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the text Fill Color. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

Keep in mind that [TextStyle.applyFill](#textstyle-applyfill) must be `true` in order for the fill color to show up. You can set it to `true` by enabling Fill in the Properties or Character panel, or by using [TextStyle.setApplyFill(value, startIndex, numOfCharacters)](#textstyle-setapplyfill).

**Parameters**

| `value`           | Required. Array of numbers. `[R, G, B]` with each value between 0.0 to 1.0.                                                 |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.applyStroke

**Description**

Returns whether Stroke is enabled.

**Type**

Boolean

---

## TextStyle.setApplyStroke(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set whether Stroke is enabled. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Boolean. Whether to enable or disable Stroke.                                                                     |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.strokeColor

**Description**

Returns the Stroke Color as RGB values on a scale from 0 - 1.0.

**Type**

Array of numbers

---

## TextStyle.setStrokeColor(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Stroke Color. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

Keep in mind that [TextStyle.applyStroke](#textstyle-applystroke) must be `true` and [TextStyle.strokeWidth](#textstyle-strokewidth) must be greater than zero in order for any stroke color to be shown. You can set these by enabling Stroke or increasing Stroke Width in the Properties or Character panel, or by using [TextStyle.setApplyStroke(value, startIndex, numOfCharacters)](#textstyle-setapplystroke) and [TextStyle.setStrokeWidth(value, startIndex, numOfCharacters)](#textstyle-setstrokewidth), respectively.

**Parameters**

| `value`           | Required. Array of numbers. `[R, G, B]` with each value between 0.0 to 1.0.                                                 |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.strokeWidth

**Description**

Returns the Stroke Width value for a Text layer.

**Type**

Number

---

## TextStyle.setStrokeWidth(`value`, `startIndex`, `numOfCharacters`)

**Description**

Used to set the Stroke Width to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

Keep in mind that [TextStyle.applyStroke](#textstyle-applystroke) must be `true` in order to see any change in stroke width. You can set this either by enabling Stroke in the Properties or Character panel, or via [TextStyle.setApplyStroke(value, startIndex, numOfCharacters)](#textstyle-setapplystroke).

**Parameters**

| `value`           | Required. Number. The value to set the Stroke Width.                                                                        |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.kerningType

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the Kerning Type for a Text layer.

**Type**

Predefined string as defined in [ReturnedKerningType](). Read-only. One of the following:

- `manual`
- `metrics`
- `optical`

---

## TextStyle.setKerningType(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to set the Kerning Type. The value will be applied to the entire Text layer unless a start index and number of characters are specified.
Please note that `manual` is not a valid value for this method. To set manual kerning, use [TextStyle.setKerning(value, characterIndex)](#textstyle-setkerning).
Also, please note that automatic kerning will take a precendence over manual kerning.

**Type**

Predefined string as defined in [KerningType](). One of the following:

- `metrics`
- `optical`

**Parameters**

| `value`           | Required. Predefined string as defined in [KerningType](). The value to set for Kerning Type.                              |
|-------------------|----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                         |
| `numOfCharacters` | Optional. Number. The length of the substring to be changed. Defaults to the number of characters until end of the string. |

**Type**

None

---

## TextStyle.kerning

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the Kerning Value for a Text Layer. For this value to be returned as anything other than zero, the [KerningType]() must not be set.

**Type**

Number. Read-only.

---

## TextStyle.setKerning(`value`, `characterIndex`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to set the Kerning Value at the specifed character index. This will only affect the Text layer when [KerningType]() is not set for the character index.

**Parameters**

| `value`          | Required. Number. The value to set the Kerning Value.                  |
|------------------|------------------------------------------------------------------------|
| `characterIndex` | Required. Number. The character index for the substring to be applied. |

**Type**

None

---

## TextStyle.tsume

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the Tsume value for a Text layer.

**Type**

Number (between 0 and 1).

---

## TextStyle.setTsume(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to set the Tsume to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Number (between 0 and 100). The value to set the Tsume.                                                           |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Type**

None

---

## TextStyle.verticalScaling

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the Vertical Scaling for a Text layer.

**Type**

Number

---

## TextStyle.setVerticalScaling(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to set the Vertical Scaling to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Number. The value to set the Vertical Scaling.                                                                    |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.horizontalScaling

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the Horizontal Scaling for a Text layer.

**Type**

Number

---

## TextStyle.setHorizontalScaling(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to set the Horizontal Scaling to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Number. The value to set the Horizontal Scaling.                                                                  |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.lineJoin

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the Line Join Type for a Text layer. The returned value is a defined string in [LineJoinType]().

**Type**

Predefined string as defined in [LineJoinType](). One of the following:

- `bevel`
- `miter`
- `round`

---

## TextStyle.setLineJoin(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to set the Line Join Type to a specified value. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Predefined string as defined in [LineJoinType](). The value to set for Line Join Type.                            |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.baselineOption

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the Baseline Option Type for a Text layer. The returned value is a defined string in [BaselineOptionType]().

**Type**

Predefined string as defined in [BaselineOptionType](). One of the following:

- `default`
- `subscript`
- `superscript`

---

## TextStyle.setBaselineOption(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to set the baseline option to a specified predefined string. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Predefined string as defined in [BaselineOptionType]() . The value to set for Baseline Option.                    |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.digitSet

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the Digit Set for a Text layer. The returned value is a defined string in [DigitSetType]().

**Type**

Predefined string as defined in [DigitSetType](). One of the following:

- `default`
- `hindidigits`

---

## TextStyle.setDigitSet(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to set the Digit Set to a specified predefined string. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Predefined string as defined in [DigitSetType]() . The value to use for Digit Set.                                |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.isLigature

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns whether ligatures are enabled.

**Type**

Boolean

---

## TextStyle.setLigature(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to enable or disable ligatures. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Boolean. Whether to enable or disable ligatures.                                                                  |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.baselineDirection

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the Baseline Direction for a Text layer. The returned value is a defined string in [BaselineDirectionType]().

**Type**

Predefined string as defined in [BaselineDirectionType](). One of the following:

- `default`
- `rotated`
- `tate-chuu-yoko`

---

## TextStyle.setBaselineDirection(`value`, `startIndex`, `numOfCharacters`)

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Used to set the Baseline Direction to a specified predefined string. The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

**Parameters**

| `value`           | Required. Predefined string as defined in [BaselineDirectionType]() . The value to set for Baseline Direction.              |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------|
| `startIndex`      | Optional. Number. The start index for the substring to be replaced. Defaults to 0.                                          |
| `numOfCharacters` | Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.justification

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the value of Justification of the first paragraph of a Text layer.

#### WARNING
The left and right values for alignment/justification will be reversed if the Text layer’s [TextStyle.direction](#textstyle-direction) is set to use right-to-left. You can control this using the Property or Paragraph panel, or via [TextStyle.setDirection(value)](#textstyle-setdirection).

**Type**

Predefined string as defined in [JustificationType](). One of the following:

- `alignCenter`
- `alignLeft`
- `alignRight`
- `justifyFull`
- `justifyLastCenter`
- `justifyLastLeft`
- `justifyLastRight`

---

## TextStyle.setJustification(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to set the Justification for the entire Text layer.

#### WARNING
The left and right values for alignment/justification will be reversed if the Text layer’s [TextStyle.direction](#textstyle-direction) is set to use right-to-left. You can control this using the Property or Paragraph panel, or via [TextStyle.setDirection(value)](#textstyle-setdirection).

**Parameters**

| `value`   | Predefined string as defined in [JustificationType](); the desired value for the Justification.   |
|-----------|---------------------------------------------------------------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.direction

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the value of Direction of the first paragraph of a Text layer.

**Type**

Predefined string as defined in [DirectionType](). One of the following:

- `left-to-right`
- `right-to-left`

---

## TextStyle.setDirection(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to set the Direction for the entire Text layer, either `left-to-right` or `right-to-left`.

**Parameters**

| `value`   | Predefined string as defined in [DirectionType](); the desired value for Direction.   |
|-----------|---------------------------------------------------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.leftMargin

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the value of Left Margin of the first paragraph of a Text layer.

**Type**

Number

---

## TextStyle.setLeftMargin(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to set the Left Margin of a Text layer to a specified value.

**Parameters**

| `value`   | Number; the desired value for Left Margin.   |
|-----------|----------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.rightMargin

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the value of Right Margin of the first paragraph of a Text layer.

**Type**

Number

---

## TextStyle.setRightMargin(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to set the Right Margin of a Text layer to a specified value.

**Parameters**

| `value`   | Number; the desired value for Right Margin.   |
|-----------|-----------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.spaceAfter

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the value of the Space After the first paragraph of a Text layer.

**Type**

Number

---

## TextStyle.setSpaceAfter(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to set the Space After attribute of a Text layer to a specified value.

**Parameters**

| `value`   | Number; the desired value for the Space After attribute.   |
|-----------|------------------------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.spaceBefore

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the value of the Space Before the first paragraph of a Text layer.

**Type**

Number

---

## TextStyle.setSpaceBefore(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to set the Space Before attribute of a Text layer to a specified value.

**Parameters**

| `value`   | Number; the desired value for the Space Before attribute.   |
|-----------|-------------------------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.firstLineIndent

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the value of First Line Indent of the first line of the first paragraph of a Text layer.

**Type**

Number

---

## TextStyle.setFirstLineIndent(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to set the First Line Indent of a Text layer to a specified value.

**Parameters**

| `value`   | Number; the desired value for First Line Indent.   |
|-----------|----------------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.isEveryLineComposer

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns ``true`` if the Text layer if Every-Line Composer is set for the first paragraph of a Text layer and ``false`` if Single-Line Composer is set for the first paragraph of a Text layer

**Type**

Boolean

---

## TextStyle.setEveryLineComposer(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to enable or disable the Every-Line Composer for the entire Text layer.

**Parameters**

| `value`   | Boolean. Whether to enable or disable Every-Line Composer.   |
|-----------|--------------------------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.isHangingRoman

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Whether Hanging Roman Punctuation is set for the entire Text layer.

**Type**

Boolean

---

## TextStyle.setHangingRoman(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to enable or disable Hanging Roman Punctuation for the entire Text layer.

**Parameters**

| `value`   | Boolean. Whether to enable or disable Roman Hanging Punctuation.   |
|-----------|--------------------------------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).

---

## TextStyle.leadingType

#### NOTE
This functionality was added in After Effects 25.0.

**Description**

Returns the value of Leading Type for the first paragraph of a Text layer.

**Type**

Predefined string as defined in [LeadingType](). One of the following:

- `bottom-to-bottom`
- `top-to-top`

---

## TextStyle.setLeadingType(`value`)

#### NOTE
This functionality was added in After Effects 25.0.

#### WARNING
This method must be called after [TextStyle.setText(value)](#textstyle-settext) if both are being used.

**Description**

Used to set the Leading Type for the entire Text layer.

**Parameters**

| `value`   | Predefined string as defined in [LeadingType](); the desired value for Leading Type.   |
|-----------|----------------------------------------------------------------------------------------|

**Returns**

A [TextStyle object](#textstyle).
