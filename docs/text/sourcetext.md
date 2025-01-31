# Source Text

`text.sourceText`

These functions are accessible on the [Text.sourceText](text.md#textsourcetext) object in AE 17.0 and later.

---

## Attributes

### SourceText.isHorizontalText

`text.sourceText.isHorizontalText`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns `true` if the Text layer is horizontal and `false` if it is vertical.

#### Type

Boolean

---

### SourceText.isParagraphText

`text.sourceText.isParagraphText`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns `true` if a Text layer is Paragraph text. If the Text layer is a Point text, it returns `false`.

#### Type

Boolean

---

### SourceText.isPointText

`text.sourceText.isPointText`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns `true` if a Text layer is Point text. If the Text layer is Paragraph text, it returns `false`.

#### Type

Boolean

---

### SourceText.isVerticalText

`text.sourceText.isVerticalText`

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns `true` if the Text layer is vertical and `false` if it is horizontal.

#### Type

Boolean

---

### SourceText.style

`text.sourceText.style`

#### Description

Returns the [Text Style](./style.md) object for a given `sourceText` property.

#### Type

[Text Style](./style.md) object

---

## Methods

### SourceText.createStyle()

`text.sourceText.createStyle()`

#### Description

Used to initialize an empty [Text Style](./style.md) object in which you'd manually bake in specific values.

#### Returns

Empty [Text Style](./style.md) object.

#### Example

To create a new style with font size 300 and the font Impact:

```js
text.sourceText
    .createStyle()
    .setFontSize(300)
    .setFont("Impact");
```

---

### SourceText.getStyleAt()

`text.sourceText.getStyleAt(charIndex[, time])`

#### Description

This function returns the [Text Style](./style.md) object of a particular character at a specific time.

In case the style is keyframed and changes over time, use the second `time` parameter to specify the target time to get the style at.

!!! note
    Using [SourceText.style](#sourcetextstyle) is the same as using `text.sourceText.getStyleAt(0,0)`

#### Parameters

| Parameter |  Type  |                                     Description                                      |
| --------- | ------ | ------------------------------------------------------------------------------------ |
| `index`   | Number | The index of the letter or character whose style is needed                           |
| `time`    | Number | Optional. The time within the composition to get the style from. Defaults to `time`. |

#### Returns

[Text Style](./style.md) object

#### Example

To get the style of the first character at the beginning of the timeline:

```js
text.sourceText.getStyleAt(0,0);
```
