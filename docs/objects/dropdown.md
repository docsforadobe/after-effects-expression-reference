# Dropdown Menus

This category contains information relating to dropdown menu properties.

!!! note
    These APIs were added in After Effects 26.0.

In expressions, the `.value` of a dropdown menu is returned as an index (a number). This is true of both customized Menu properties of Dropdown Menu Controls and dropdown menus of other effects and layers. **The strings in dropdown menu properties of effects and layers are also accessible via the properties/methods below.**

On this page, `effect("Dropdown Menu Control")("Menu")` is used as a sample on how to call these items; however, note that any method that returns a dropdown menu [Property](../objects/property.md) will work.

**Notes**

- These APIs are available only in expressions using the JavaScript expression engine.

- The text of `Layer Control` dropdowns is not accessible with these APIs. If you need the selected layer's name, you can use the `.name` property of the layer returned by the Layer Control.

!!! warning
    We recommend continuing to use the index of dropdown menus when driving expression logic (versus matching the strings), since indexes will remain unchanged when the language of After Effects changes.

---

## Attributes

### items

`effect("Dropdown Menu Control")("Menu").items`

#### Description

Returns an array of all the text strings in a dropdown menu property.

#### Type

Array of Strings

#### Example

**Show all the strings in a dropdown on separate lines:**

```js
const menu = effect("Dropdown Menu Control")("Menu");
const allStrings = menu.items;

allStrings.join("\n");
```

---

### text

`effect("Dropdown Menu Control")("Menu").text`

#### Description

Returns the currently-active text string of a dropdown menu property at the current time.

#### Type

String

#### Example

**Show the selected dropdown text directly in a Text layer:**

```js
effect("Dropdown Menu Control")("Menu").text;
```

**Show the current Fractal Type from the native Fractal Noise effect:**

```js
effect("ADBE Fractal Noise")("ADBE Fractal Noise-0001").text;
```

---

## Methods

### textAtTime()

`effect("Dropdown Menu Control")("Menu").textAtTime(time)`

#### Description

Returns the text string of a dropdown menu property at the specified time, in seconds.

This is effectively the same as how `valueAtTime()` relates to `value`, in that `text` will always return the dropdown string as the current time, and `timeAtTime()` can return the string at a specific time.

#### Parameters

| Parameter |  Type  |                    Description                    |
| --------- | ------ | ------------------------------------------------- |
| `time`    | Number | The time, in seconds, to get the text string from |

#### Returns

String

