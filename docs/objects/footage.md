# Footage

`footage("myFile")`

To use a footage item from the Project panel as an object in an expression, use the global footage method, as in `footage("myFile")`.

You can also access a footage object using the source attribute on a layer whose source is a footage item (i.e. `thisLayer.source`)

!!! info
    On this page, we're going to use `footage("myFile")` as a demonstration on how to use these items, however note that any method that returns a [Footage object](#) will work.

---

## Attributes

### Footage.duration

`footage("myFile").duration`

#### Description

Returns the duration of the footage item, in seconds.

#### Type

Number

---

### Footage.frameDuration

`footage("myFile").frameDuration`

#### Description

Returns the duration of a frame in the footage item, in seconds.

#### Type

Number

---

### Footage.height

`footage("myFile").height`

#### Description

Returns the height of the footage item, in pixels.

#### Type

Number

---

### Footage.name

`footage("myFile").name`

#### Description

Returns the name of the footage item as shown in the Project panel.

#### Type

String

---

### Footage.ntscDropFrame

`footage("myFile").ntscDropFrame`

!!! note
    This functionality was added in After Effects CS5.5

#### Description

Returns `true` if the timecode is in drop-frame format.

#### Type

Boolean

---

### Footage.pixelAspect

`footage("myFile").pixelAspect`

#### Description

Returns the pixel aspect ratio of the footage item.

#### Type

Number

---

### Footage.sourceData

`footage("myFile").sourceData`

#### Description

Returns the data of a JSON file as an array of `sourceData` objects.

The structure of the JSON file will determine the size and complexity of the array.

Individual data streams can be referenced as hierarchal attributes of the data.

#### Type

An array of `sourceData` objects; read-only.

#### Example

Given a data stream named "Color", the following will return the value of "Color" from the first data object:

```js
footage("sample.json").sourceData[0].Color
```

Typical use is to assign a JSON file's `sourceData` to a variable, and then reference the desired data stream. For example:

```js
const myData = footage("sample.json").sourceData;
myData[0].Color;
```

---

### Footage.sourceText

`footage("myFile").sourceText`

#### Description

Returns the contents of a JSON file as a string.

The `eval()` method can be used to convert the string to an array of sourceData objects, identical to the results of the [Footage.sourceData](#footagesourcedata) attribute, from which the individual data streams can be referenced as hierarchal attributes of the data.

#### Type

String, the contents of the JSON file; read-only.

#### Example

```js
const myData = eval(footage("sample.json").sourceText);
myData.sampleValue;
```

---

### Footage.width

`footage("myFile").width`

#### Description

Returns the width of the footage item, in pixels.

#### Type

Number

---

## Methods

### Footage.dataKeyCount()

`footage("myFile").dataKeyCount(dataPath)`

#### Description

Returns the number of samples in a specificed dynamic data stream in a MGJSON file.

Accepts a single array value to define the path in the hierarchy to the desired dynamic data stream.

#### Parameters

| Parameter  | Type  |                               Description                               |
| ---------- | ----- | ----------------------------------------------------------------------- |
| `dataPath` | Array | Required. The path in the hierarchy to a static or dynamic data stream. |

#### Returns

The number of samples in the dynamic data stream.

#### Example

To return the count of samples for the first child:

```js
footage("sample.mgjson").dataKeyCount([0])
```

To return the count of samples for the second group:

```js
footage("sample.mgjson").dataKeyCount([1][0])
```

---

### Footage.dataKeyTimes()

`footage("myFile").dataKeyTimes(dataPath[, t0=startTime][, t1=endTime])`

#### Description

Returns the time in seconds for the samples of a specificed dynamic data stream in a MGJSON file.

Optionally specify the time span from which to return samples. By default the time for all samples between `startTime` and `endTime` in the dynamicdata stream are returned, as defined by the data stream's `samplesTemporalExtent` property in the MGJSON file.

Accepts a single array value to define the path in the hierarchy to the desired dynamic data stream.

#### Parameters

| Parameter  |  Type  |                                               Description                                                |
| ---------- | ------ | -------------------------------------------------------------------------------------------------------- |
| `dataPath` | Array  | Required. The path in the hierarchy to a static or dynamic data stream.                                  |
| `t0`       | Number | Optional. The start time, in seconds, of the span from which to return samples. Defaults to `startTime`. |
| `t1`       | Number | Optional. The end time, in seconds, of the span from which to return samples. Defaults to `endTime`.     |

#### Returns

Array of numbers representing the sample times.

#### Example

Return the times of samples between 1 second and 3 seconds for the first child:

```js
footage("sample.mgjson").dataKeyTimes([0], 1, 3)
```

---

### Footage.dataKeyValues()

`footage("myFile").dataKeyValues(dataPath[, t0=startTime][, t1=endTime])`

#### Description

Returns the values for the samples of a specificed dynamic data stream in a MGJSON file.

Optionally specify the time span from which to return samples. By default the time for all samples between startTime and endTime in the dynamicdata stream are returned, as defined by the data stream's `samplesTemporalExtent` property in the MGJSON file.

Accepts a single array value to define the path in the hierarchy to the desired dynamic data stream.

#### Parameters

| Parameter  |  Type  |                                               Description                                                |
| ---------- | ------ | -------------------------------------------------------------------------------------------------------- |
| `dataPath` | Array  | Required. The path in the hierarchy to a static or dynamic data stream.                                  |
| `t0`       | Number | Optional. The start time, in seconds, of the span from which to return samples. Defaults to `startTime`. |
| `t1`       | Number | Optional. The end time, in seconds, of the span from which to return samples. Defaults to `endTime`.     |

#### Returns

Array of numbers representing the sample values.

#### Example

Return the values of samples between 1 second and 3 seconds for the first child:

```js
footage("sample.mgjson").dataKeyValues([0], 1, 3)
```

---

### Footage.dataValue()

`footage("myFile").dataValue(dataPath)`

#### Description

Returns the value of specificed static or dynamic data stream in a MGJSON file.

Accepts a single array value to define the path in the hierarchy to the desired data stream.

#### Parameters

| Parameter  | Type  |                               Description                               |
| ---------- | ----- | ----------------------------------------------------------------------- |
| `dataPath` | Array | Required. The path in the hierarchy to a static or dynamic data stream. |

#### Returns

The value of the data stream.

#### Example

To return data of the first child:

```js
footage("sample.mgjson").dataValue([0])
```

To return data of the first child in the second group:

```js
footage("sample.mgjson").dataValue([1][0])
```
