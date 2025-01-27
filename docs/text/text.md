# Text

`text`

This category holds generic text-related entries for text layers.

---

## Attributes

### Text.sourceText

`text.sourceText`

#### Description

Returns the text content of a text layer.

!!! note
    As of After Effects 17.0, this property returns the [Source Text](./sourcetext.md) object to access text style properties. If no style properties are specified, this returns the text content as expected.

#### Type

String of text content, or [Source Text](./sourcetext.md) (AE 17.0+)

---

### Text.Font...

#### Description

!!! note
    This isn't actually an expression method! Instead, it's a button from the expression fly-out menu.

Launches a dialog window for the user to specify a font name and weight.

Upon selection, the internal font name is injected into the expression editor as a string.

#### Type

String
