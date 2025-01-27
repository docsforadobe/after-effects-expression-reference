# Source Text

These functions are accessible on the [Text.sourceText](text.md#textsourcetext) object in AE 17.0 and later.

---

## SourceText.style

#### Description

Returns the [Text Style](text-style.md#textstyle) object for a given `sourceText` property.

#### Type

[Text Style](text-style.md#textstyle) object

---

## SourceText.getStyleAt(`charIndex`, `t = time`)

#### Description

This function returns the [Text Style](text-style.md#textstyle) object of a particular character at a specific time.

In case the style is keyframed and changes over time, use the second `time` parameter to specify the target time to get the style at.

!!! note
    Using [SourceText.style](#sourcetextstyle) is the same as using `text.sourceText.getStyleAt(0,0)`

For example, to get the style of the first character at the beginning of the timeline:

```js
text.sourceText.getStyleAt(0,0);
```

#### Parameters

| `index`   | Number | The index of the letter or character whose style is needed                           |
|-----------|----------------------------------------------------------------------------------------------|
| `time`    | Number | Optional. The time within the composition to get the style from. Defaults to `time`. |

#### Type

[Text Style](text-style.md#textstyle) object

---

## SourceText.createStyle()

#### Description

Used to initialize an empty [Text Style](text-style.md#textstyle) object in which you'd manually bake in specific values.

For example, to create a new style with font size 300 and the font Impact:

```js
text.sourceText.createStyle().setFontSize(300).setFont("Impact");
```

#### Parameters

None.

#### Type

Empty [Text Style](text-style.md#textstyle) object.

---

## SourceText.isVerticalText

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns `true` if the Text layer is vertical and `false` if it is horizontal.

#### Parameters

None.

#### Type

Boolean

---

## SourceText.isHorizontalText

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns `true` if the Text layer is horizontal and `false` if it is vertical.

#### Parameters

None.

#### Type

Boolean

---

## SourceText.isPointText

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns `true` if a Text layer is Point text. If the Text layer is Paragraph text, it returns `false`.

#### Parameters

None.

#### Type

Boolean

---

## SourceText.isParagraphText

!!! note
    This functionality was added in After Effects 25.0.

#### Description

Returns `true` if a Text layer is Paragraph text. If the Text layer is a Point text, it returns `false`.

#### Parameters

None.

#### Type

Boolean
