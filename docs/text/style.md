# Text Style

`text.sourceText.style`

Most of these functions are accessible from the [SourceText.style](./sourcetext.md#sourcetextstyle) object in AE 17.0 and later. Where noted, additional methods were added in AE 25.0. The ability to control percharacter styling was also added in 25.0. Use the second and third arguments (when available) to control per-character styling.

!!! note
    When using per-character styling, line breaks and spaces are also considered characters and must be accounted for (or skipped, if desired) when calcuating character indexes.

For more info on working with text styles, see:

- [Use Expressions to Edit and Access Text Properties on helpx.adobe.com](https://helpx.adobe.com/after-effects/user-guide.html/after-effects/using/expressions-text-properties.ug.html)
- [After Effects 2020: Express Yourself (and Your Text) on blog.adobe.com](https://blog.adobe.com/en/publish/2020/01/24/after-effects-2020-express-yourself-and-your-text)

### Chaining

All the methods for [Text Style](#text-style) will return a [Text Style](#text-style) object, so you can call them in a chain, e.g.:

```js
text.sourceText.style.setFont("Times New Roman").setFontSize(42).setText("New Text");
```

!!! tip
    You can also format this chain with line breaks to make it easier to read:
    ```js
    text.sourceText.style
        .setFont("Times New Roman")
        .setFontSize(42)
        .setText("New Text");
    ```

---

## Attributes

### TextStyle.applyFill

`text.sourceText.style.applyFill`

#### Description

Returns whether Fill Color is enabled.

#### Type

Boolean

---

### TextStyle.applyStroke

`text.sourceText.style.applyStroke`

#### Description

Returns whether Stroke is enabled.

#### Type

Boolean

---

### TextStyle.baselineDirection

`text.sourceText.style.baselineDirection`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the Baseline Direction for a Text layer.

#### Type

Predefined string. One of:

- `default`
- `rotated`
- `tate-chuu-yoko`

---

### TextStyle.baselineOption

`text.sourceText.style.baselineOption`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the Baseline Option Type for a Text layer.

#### Type

Predefined string. One of:

- `default`
- `subscript`
- `superscript`

---

### TextStyle.baselineShift

`text.sourceText.style.baselineShift`

#### Description

Returns the value of Baseline Shift for a Text layer.

#### Type

Number

---

### TextStyle.digitSet

`text.sourceText.style.digitSet`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the Digit Set for a Text layer.

#### Type

Predefined string. One of:

- `default`
- `hindidigits`

---

### TextStyle.direction

`text.sourceText.style.direction`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the value of Direction of the first paragraph of a Text layer.

#### Type

Predefined string. One of:

- `left-to-right`
- `right-to-left`

---

### TextStyle.fillColor

`text.sourceText.style.fillColor`

#### Description

Returns the text Fill Color as RGB values on a scale from 0 - 1.0.

#### Type

Array of Numbers.

---

### TextStyle.firstLineIndent

`text.sourceText.style.firstLineIndent`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the value of First Line Indent of the first line of the first paragraph of a Text layer.

#### Type

Number

---

### TextStyle.font

`text.sourceText.style.font`

#### Description

Returns the font name for a Text layer.

#### Type

String

---

### TextStyle.fontSize

`text.sourceText.style.fontSize`

#### Description

Returns the value of Font Size for a Text layer.

#### Type

Number

---

### TextStyle.horizontalScaling

`text.sourceText.style.horizontalScaling`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the Horizontal Scaling for a Text layer.

#### Type

Number

---

### TextStyle.isAllCaps

`text.sourceText.style.isAllCaps`

#### Description

Returns whether All Caps is enabled.

#### Type

Boolean

---

### TextStyle.isAutoLeading

`text.sourceText.style.isAutoLeading`

#### Description

Returns whether Auto Leading is enabled.

#### Type

Boolean

---

### TextStyle.isEveryLineComposer

`text.sourceText.style.isEveryLineComposer`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns `true` if the Text layer if Every-Line Composer is set for the first paragraph of a Text layer and `false` if Single-Line Composer is set for the first paragraph of a Text layer

#### Type

Boolean

---

### TextStyle.isFauxBold

`text.sourceText.style.isFauxBold`

#### Description

Returns whether Faux Bold is enabled.

#### Type

Boolean

---

### TextStyle.isFauxItalic

`text.sourceText.style.isFauxItalic`

#### Description

Returns whether Faux Italics are enabled.

#### Type

Boolean

---

### TextStyle.isHangingRoman

`text.sourceText.style.isHangingRoman`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Whether Hanging Roman Punctuation is set for the entire Text layer.

#### Type

Boolean

---

### TextStyle.isLigature

`text.sourceText.style.isLigature`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns whether ligatures are enabled.

#### Type

Boolean

---

### TextStyle.isSmallCaps

`text.sourceText.style.isSmallCaps`

#### Description

Returns whether Small Caps is enabled.

#### Type

Boolean

---

### TextStyle.justification

`text.sourceText.style.justification`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the value of Justification of the first paragraph of a Text layer.

!!! warning
    The left and right values for alignment/justification will be reversed if the Text layer's [TextStyle.direction](#textstyledirection) is set to use right-to-left. You can control this using the Property or Paragraph panel, or via [TextStyle.setDirection()](#textstylesetdirection).

#### Type

Predefined string. One of:

- `alignCenter`
- `alignLeft`
- `alignRight`
- `justifyFull`
- `justifyLastCenter`
- `justifyLastLeft`
- `justifyLastRight`

---

### TextStyle.kerning

`text.sourceText.style.kerning`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the Kerning Value for a Text Layer.

For this value to be returned as anything other than zero, the [KerningType](#textstylekerningtype) must not be set.

#### Type

Number. Read-only.

---

### TextStyle.kerningType

`text.sourceText.style.kerningType`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the Kerning Type for a Text layer.

#### Type

Read-only. Predefined string. One of:

- `manual`
- `metrics`
- `optical`

---

### TextStyle.leading

`text.sourceText.style.leading`

#### Description

Returns the value of Leading for a Text layer.

#### Type

Number

---

### TextStyle.leadingType

`text.sourceText.style.leadingType`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the value of Leading Type for the first paragraph of a Text layer.

#### Type

Predefined string. One of:

- `bottom-to-bottom`
- `top-to-top`

---

### TextStyle.leftMargin

`text.sourceText.style.leftMargin`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the value of Left Margin of the first paragraph of a Text layer.

#### Type

Number

---

### TextStyle.lineJoin

`text.sourceText.style.lineJoin`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the Line Join Type for a Text layer.

#### Type

Predefined string. One of:

- `bevel`
- `miter`
- `round`

---

### TextStyle.rightMargin

`text.sourceText.style.rightMargin`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the value of Right Margin of the first paragraph of a Text layer.

#### Type

Number

---

### TextStyle.spaceAfter

`text.sourceText.style.spaceAfter`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the value of the Space After the first paragraph of a Text layer.

#### Type

Number

---

### TextStyle.spaceBefore

`text.sourceText.style.spaceBefore`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the value of the Space Before the first paragraph of a Text layer.

#### Type

Number

---

### TextStyle.strokeColor

`text.sourceText.style.strokeColor`

#### Description

Returns the Stroke Color as RGB values on a scale from 0 - 1.0.

#### Type

Array of numbers

---

### TextStyle.strokeWidth

`text.sourceText.style.strokeWidth`

#### Description

Returns the Stroke Width value for a Text layer.

#### Type

Number

---

### TextStyle.tracking

`text.sourceText.style.tracking`

#### Description

Returns the value of Tracking for a Text layer.

#### Type

Number

---

### TextStyle.tsume

`text.sourceText.style.tsume`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the Tsume value for a Text layer.

#### Type

Number (between `0` and `1`).

---

### TextStyle.verticalScaling

`text.sourceText.style.verticalScaling`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns the Vertical Scaling for a Text layer.

#### Type

Number

---

## Methods

### TextStyle.replaceText()

`text.sourceText.style.replaceText(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

This is used when you want to define (or inherit) a [Text Style](#text-style), while setting the content for a substring of the text.

#### Parameters

|     Parameter     |  Type  | Description |                                                                                                           |
| ----------------- | ------ | ----------- | --------------------------------------------------------------------------------------------------------- |
| `value`           | String | Required.   | The text to set.                                                                                          |
| `startIndex`      | Number | Optional.   | The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional.   | The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

#### Example

To create a custom style and then set a substring of the text within the expression:

```js
// assume the value of the source text is "Old Text"
const referenceText = thisComp.layer("Source Layer Name").text.sourceText;
const style = referenceText.getStyleAt(0,0);

// This will change the text from "Old Text" to "NewText" as the first 4 characters are replaced.
style.replaceText("New", 0, 4);
```

---

### TextStyle.setAllCaps()

`text.sourceText.style.setAllCaps(value[, startIndex, numOfCharacters])`

#### Description

Used to set the All Caps status.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type   |                                                     Description                                                     |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Boolean | Required. Whether to enable or disable All Caps.                                                                    |
| `startIndex`      | Number  | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number  | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setApplyFill()

`text.sourceText.style.setApplyFill(value[, startIndex, numOfCharacters])`

#### Description

Used to set whether Fill Color is enabled.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type   |                                                     Description                                                     |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Boolean | Required. Whether to enable or disable Fill.                                                                        |
| `startIndex`      | Number  | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number  | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setApplyStroke()

`text.sourceText.style.setApplyStroke(value[, startIndex, numOfCharacters])`

#### Description

Used to set whether Stroke is enabled.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type   |                                                     Description                                                     |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Boolean | Required. Whether to enable or disable Stroke.                                                                      |
| `startIndex`      | Number  | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number  | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setAutoLeading()

`text.sourceText.style.setAutoLeading(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Auto Leading status.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type   |                                                     Description                                                     |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Boolean | Required. Whether to enable or disable Auto Leading.                                                                |
| `startIndex`      | Number  | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number  | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setBaselineDirection()

`text.sourceText.style.setBaselineDirection(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to set the Baseline Direction.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |                                      Type                                       |                                                     Description                                                     |
| ----------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Predefined string as defind in [BaselineDirection](#textstylebaselinedirection) | The value to set for Baseline Direction.                                                                            |
| `startIndex`      | Number                                                                          | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number                                                                          | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setBaselineShift()

`text.sourceText.style.setBaselineShift(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Baseline Shift to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type  |                                                     Description                                                     |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Number | Required. The Baseline Shift value to set.                                                                          |
| `startIndex`      | Number | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setBaselineOption()

`text.sourceText.style.setBaselineOption(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to set the baseline option.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |                                   Type                                    |                                                     Description                                                     |
| ----------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Predefined string as defind in [BaselineOption](#textstylebaselineoption) | Required. The value to set for Baseline Option.                                                                     |
| `startIndex`      | Number                                                                    | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number                                                                    | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setDigitSet()

`text.sourceText.style.setDigitSet(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to set the Digit Set.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |                             Type                              |                                                     Description                                                     |
| ----------------- | ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Predefined string as defind in [DigitSet](#textstyledigitset) | Required. The value to use for Digit Set.                                                                           |
| `startIndex`      | Number                                                        | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number                                                        | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setDirection()

`text.sourceText.style.setDirection(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to set the Direction for the entire Text layer, either `left-to-right` or `right-to-left`.

#### Parameters

| Parameter |                               Type                               |           Description            |
| --------- | ---------------------------------------------------------------- | -------------------------------- |
| `value`   | Predefined string as defined in [Direction](#textstyledirection) | The desired value for Direction. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setEveryLineComposer()

`text.sourceText.style.setEveryLineComposer(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to enable or disable the Every-Line Composer for the entire Text layer.

#### Parameters

| Parameter |  Type   |                    Description                    |
| --------- | ------- | ------------------------------------------------- |
| `value`   | Boolean | Whether to enable or disable Every-Line Composer. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setFauxBold()

`text.sourceText.style.setFauxBold(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Faux Bold status.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type   |                                                     Description                                                     |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Boolean | Required. Whether to enable or disable Faux Bold.                                                                   |
| `startIndex`      | Number  | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number  | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setFauxItalic()

`text.sourceText.style.setFauxItalic(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Faux Italics status.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type   |                                                     Description                                                     |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Boolean | Required. Whether to enable or disable Faux Italics.                                                                |
| `startIndex`      | Number  | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number  | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setFillColor()

`text.sourceText.style.setFillColor(value[, startIndex, numOfCharacters])`

#### Description

Used to set the text Fill Color.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

Keep in mind that [TextStyle.applyFill](#textstyleapplyfill) must be `true` in order for the fill color to show up. You can set it to `true` by enabling Fill in the Properties or Character panel, or by using [TextStyle.setApplyFill()](#textstylesetapplyfill).

#### Parameters

|     Parameter     |       Type       |                                                     Description                                                     |
| ----------------- | ---------------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Array of numbers | Required. `[R, G, B]` with each value between `0.0` and `1.0`.                                                      |
| `startIndex`      | Number           | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number           | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setFirstLineIndent()

`text.sourceText.style.setFirstLineIndent(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to set the First Line Indent of a Text layer to a specified value.

#### Parameters

| Parameter |  Type  |               Description                |
| --------- | ------ | ---------------------------------------- |
| `value`   | Number | The desired value for First Line Indent. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setFont()

`text.sourceText.style.setFont(value[, startIndex, numOfCharacters])`

#### Description

Used to set the font to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type  |                                                     Description                                                     |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | String | Required. The font to set.                                                                                          |
| `startIndex`      | Number | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setFontSize()

`text.sourceText.style.setFontSize(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Font Size to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type  |                                                     Description                                                     |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Number | Required. The Font Size to set.                                                                                     |
| `startIndex`      | Number | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---


### TextStyle.setHangingRoman()

`text.sourceText.style.setHangingRoman(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to enable or disable Hanging Roman Punctuation for the entire Text layer.

#### Parameters

| Parameter |  Type   |                       Description                       |
| --------- | ------- | ------------------------------------------------------- |
| `value`   | Boolean | Whether to enable or disable Roman Hanging Punctuation. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setHorizontalScaling()

`text.sourceText.style.setHorizontalScaling(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to set the Horizontal Scaling to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type  |                                                     Description                                                     |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Number | Required. The value to set the Horizontal Scaling.                                                                  |
| `startIndex`      | Number | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setJustification()

`text.sourceText.style.setJustification(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to set the Justification for the entire Text layer.

!!! warning
    The left and right values for alignment/justification will be reversed if the Text layer's [TextStyle.direction](#textstyledirection) is set to use right-to-left. You can control this using the Property or Paragraph panel, or via [TextStyle.setDirection()](#textstylesetdirection).

#### Parameters

| Parameter |                                   Type                                   |               Description                |
| --------- | ------------------------------------------------------------------------ | ---------------------------------------- |
| `value`   | Predefined string as defined in [Justification](#textstylejustification) | The desired value for the Justification. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setKerning()

`text.sourceText.style.setKerning(value, characterIndex)`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to set the Kerning Value at the specifed character index.

This will only affect the Text layer when [KerningType](#textstylekerningtype) is not set for the character index.

#### Parameters

|    Parameter     |  Type  |                          Description                           |
| ---------------- | ------ | -------------------------------------------------------------- |
| `value`          | Number | Required. The value to set the Kerning Value.                  |
| `characterIndex` | Number | Required. The character index for the substring to be applied. |

#### Returns

None

---

### TextStyle.setKerningType()

`text.sourceText.style.setKerningType(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to set the Kerning Type.

The value will be applied to the entire Text layer unless a start index and number of characters are specified.

!!! note
    `manual` is not a valid value for this method. To set manual kerning, use [TextStyle.setKerning()](#textstylesetkerning).

    Also, note that automatic kerning will take a precendence over manual kerning.

#### Parameters

|     Parameter     |                                    Type                                     |                                                    Description                                                     |
| ----------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `value`           | `metrics` or `optical`, as defined in [KerningType](#textstylekerningtype). | Required. The value to set for Kerning Type.                                                                       |
| `startIndex`      | Number                                                                      | Optional. The start index for the substring to be replaced. Defaults to `0`.                                       |
| `numOfCharacters` | Number                                                                      | Optional. The length of the substring to be changed. Defaults to the number of characters until end of the string. |

#### Returns

None

---

### TextStyle.setLeading()

`text.sourceText.style.setLeading(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Leading to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

Keep in mind that [TextStyle.isAutoLeading](#textstyleisautoleading) must be `false` in order for `setLeading()` to have any visible affect. You can set Leading to a value other than Auto in the Properties or Character panel, or via [TextStyle.setAutoLeading()](#textstylesetautoleading).

#### Parameters

|     Parameter     |  Type  |                                                     Description                                                     |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Number | Required. The Leading value to set.                                                                                 |
| `startIndex`      | Number | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setLeadingType()

`text.sourceText.style.setLeadingType(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to set the Leading Type for the entire Text layer.

#### Parameters

| Parameter |                                 Type                                 |             Description             |     |
| --------- | -------------------------------------------------------------------- | ----------------------------------- | --- |
| `value`   | Predefined string as defined in [LeadingType](#textstyleleadingtype) | The desired value for Leading Type. |     |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setLeftMargin()

`text.sourceText.style.setLeftMargin(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to set the Left Margin of a Text layer to a specified value.

#### Parameters

| Parameter |  Type  |            Description             |
| --------- | ------ | ---------------------------------- |
| `value`   | Number | The desired value for Left Margin. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setLigature()

`text.sourceText.style.setLigature(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to enable or disable ligatures.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type   |                                                     Description                                                     |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Boolean | Required. Whether to enable or disable ligatures.                                                                   |
| `startIndex`      | Number  | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number  | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setLineJoin()

`text.sourceText.style.setLineJoin(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to set the Line Join Type to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |                              Type                              |                                                     Description                                                     |
| ----------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Predefined string as defined in [LineJoin](#textstylelinejoin) | Required. The value to set for Line Join Type.                                                                      |
| `startIndex`      | Number                                                         | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number                                                         | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setRightMargin()

`text.sourceText.style.setRightMargin(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to set the Right Margin of a Text layer to a specified value.

#### Parameters

| Parameter |  Type  |             Description             |
| --------- | ------ | ----------------------------------- |
| `value`   | Number | The desired value for Right Margin. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setSmallCaps()

`text.sourceText.style.setSmallCaps(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Small Caps status.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type   |                                                     Description                                                     |
| ----------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Boolean | Required. Whether to enable or disable Small Caps.                                                                  |
| `startIndex`      | Number  | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number  | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setSpaceAfter()

`text.sourceText.style.setSpaceAfter(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to set the Space After attribute of a Text layer to a specified value.

#### Parameters

| Parameter |  Type  |                   Description                    |
| --------- | ------ | ------------------------------------------------ |
| `value`   | Number | The desired value for the Space After attribute. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setSpaceBefore()

`text.sourceText.style.setSpaceBefore(value)`

!!! note
    This functionality was added in After Effects 25.0.

!!! warning
    This method must be called after [TextStyle.setText()](#textstylesettext) if both are being used.

#### Description

Used to set the Space Before attribute of a Text layer to a specified value.

#### Parameters

| Parameter |  Type  |                    Description                    |
| --------- | ------ | ------------------------------------------------- |
| `value`   | Number | The desired value for the Space Before attribute. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setStrokeColor()

`text.sourceText.style.setStrokeColor(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Stroke Color.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

Keep in mind that [TextStyle.applyStroke](#textstyleapplystroke) must be `true` and [TextStyle.strokeWidth](#textstylestrokewidth) must be greater than zero in order for any stroke color to be shown. You can set these by enabling Stroke or increasing Stroke Width in the Properties or Character panel, or by using [TextStyle.setApplyStroke()](#textstylesetapplystroke) and [TextStyle.setStrokeWidth()](#textstylesetstrokewidth), respectively.

#### Parameters

|     Parameter     |       Type       |                                                     Description                                                     |
| ----------------- | ---------------- | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Array of numbers | Required. `[R, G, B]` with each value between `0.0` and `1.0`.                                                      |
| `startIndex`      | Number           | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number           | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setStrokeWidth()

`text.sourceText.style.setStrokeWidth(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Stroke Width to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

Keep in mind that [TextStyle.applyStroke](#textstyleapplystroke) must be `true` in order to see any change in stroke width. You can set this either by enabling Stroke in the Properties or Character panel, or via [TextStyle.setApplyStroke()](#textstylesetapplystroke).

#### Parameters

|     Parameter     |  Type  |                                                     Description                                                     |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Number | Required. The value to set the Stroke Width.                                                                        |
| `startIndex`      | Number | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setText()

`text.sourceText.style.setText(value)`

#### Description

This is used when you want to define (or inherit) a [Text Style](#text-style) while setting the text content separately.

#### Parameters

| Parameter |  Type  |   Description    |
| --------- | ------ | ---------------- |
| `value`   | String | The text to set. |

#### Returns

A [TextStyle object](#text-style).

#### Examples

To inherit the style and content from another layer:

```js
const referenceText = thisComp.layer("Source Layer Name").text.sourceText;

const style = referenceText.getStyleAt(0, 0);
style.setText(referenceText);
```

To create a custom style and then set the text within the expression:

```js
text.sourceText
    .createStyle()
    .setFontSize(300)
    .setFont("Impact")
    .setText("Hello world!");
```

---

### TextStyle.setTracking()

`text.sourceText.style.setTracking(value[, startIndex, numOfCharacters])`

#### Description

Used to set the Tracking to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type  |                                                     Description                                                     |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Number | Required. The Tracking value to set.                                                                                |
| `startIndex`      | Number | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).

---

### TextStyle.setTsume()

`text.sourceText.style.setTsume(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to set the Tsume to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type  |                                                     Description                                                     |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Number | Required. The value to set the Tsume, between `0` and `100`.                                                        |
| `startIndex`      | Number | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

None

---

### TextStyle.setVerticalScaling()

`text.sourceText.style.setVerticalScaling(value[, startIndex, numOfCharacters])`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Used to set the Vertical Scaling to a specified value.

The value will be set for the entire Text layer unless `startIndex` and `numOfCharacters` are specified.

#### Parameters

|     Parameter     |  Type  |                                                     Description                                                     |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------- |
| `value`           | Number | Required. The value to set the Vertical Scaling.                                                                    |
| `startIndex`      | Number | Optional. The start index for the substring to be replaced. Defaults to `0`.                                        |
| `numOfCharacters` | Number | Optional. The length of the substring to be replaced. Defaults to the number of characters until end of the string. |

#### Returns

A [TextStyle object](#text-style).
