# Footage

#### Description

To use a footage item from the Project panel as an object in an expression, use the global footage method, as in `footage("file_name")`. You can also access a footage object using the source attribute on a layer whose source is a footage item.

---

## Footage.width

#### Description

Returns the width of the footage item, in pixels.

#### Type

Number

---

## Footage.height

#### Description

Returns the height of the footage item, in pixels.

#### Type

Number

---

## Footage.duration

#### Description

Returns the duration of the footage item, in seconds.

#### Type

Number

---

## Footage.frameDuration

#### Description

Returns the duration of a frame in the footage item, in seconds.

#### Type

Number

---

## Footage.ntscDropFrame

#### Description

Returns true if the timecode is in drop-frame format. (After Effects CS5.5 and later.)

#### Type

Boolean

---

## Footage.pixelAspect

#### Description

Returns the pixel aspect ratio of the footage item.

#### Type

Number

---

## Footage.name

#### Description

Returns the name of the footage item as shown in the Project panel.

#### Type

String

---

## Footage.sourceText

#### Description

Returns the contents of a JSON file as a string.

The `eval()` method can be used to convert the string to an array of sourceData objects, identical to the results of the [Footage.sourceData](#footagesourcedata) attribute, from which the individual data streams can be referenced as hierarchal attributes of the data.

For example:

```default
var myData = eval(footage("sample.json").sourceText);
myData.sampleValue;
```

#### Type

String, the contents of the JSON file; read-only.

---

## Footage.sourceData

#### Description

Returns the data of a JSON file as an array of sourceData objects.

The structure of the JSON file will determine the size and complexity of the array.

Individual data streams can be referenced as hierarchal attributes of the data.

For example, given a data stream named "Color", the following will return the value of "Color" from the first data object:

```default
footage("sample.json").sourceData[0].Color
```

Typical use is to assign a JSON file's `sourceData` to a variable, and then reference the desired data stream. For example:

```default
var myData = footage("sample.json").sourceData;
myData[0].Color;
```

#### Type

An array of sourceData objects; read-only.

---

## Footage.dataValue(`dataPath`)

#### Description

Returns the value of specificed static or dynamic data stream in a MGJSON file.

Accepts a single array value to define the path in the hierarchy to the desired data stream.

For example, to return data of the first child:

```default
footage("sample.mgjson").dataValue([0])
```

Or to return data of the first child in the second group:

```default
footage("sample.mgjson").dataValue([1][0])
```

#### Parameters

| `dataPath`   | Array, required. The path in the hierarchy to a static or dynamic data stream.   |
|--------------|----------------------------------------------------------------------------------|

#### Type

The value of the data stream.

---

## Footage.dataKeyCount(`dataPath`)

#### Description

Returns the number of samples in a specificed dynamic data stream in a MGJSON file.

Accepts a single array value to define the path in the hierarchy to the desired dynamic data stream.

For example, to return the count of samples for the first child:

```default
footage("sample.mgjson").dataKeyCount([0])
```

Or to return the count of samples for the second group:

```default
footage("sample.mgjson").dataKeyCount([1][0])
```

#### Parameters

| `dataPath`   | Array, required. The path in the hierarchy to a static or dynamic data stream.   |
|--------------|----------------------------------------------------------------------------------|

#### Type

The number of samples in the dynamic data stream.

---

## Footage.dataKeyTimes(`dataPath`, `t0 = startTime`, `t1 = endTime`)

#### Description

Returns the time in seconds for the samples of a specificed dynamic data stream in a MGJSON file.

Optionally specify the time span from which to return samples. By default the time for all samples between `startTime` and `endTime` in the dynamicdata stream are returned, as defined by the data stream's `samplesTemporalExtent` property in the MGJSON file.

Accepts a single array value to define the path in the hierarchy to the desired dynamic data stream.

The following example returns the times of samples between 1 second and 3 seconds for the first child:

```default
footage("sample.mgjson").dataKeyTimes([0], 1, 3)
```

#### Parameters

| `dataPath`   | Array, required. The path in the hierarchy to a static or dynamic data stream.                                   |
|--------------|------------------------------------------------------------------------------------------------------------------|
| `t0`         | Number, optional. The start time, in seconds, of the span from which to return samples. Defaults to `startTime`. |
| `t1`         | Number, optional. The end time, in seconds, of the span from which to return samples. Defaults to `endTime`.     |

#### Type

Array of numbers representing the sample times.

---

## Footage.dataKeyValues(`dataPath`, `t0 = startTime`, `t1 = endTime`)

#### Description

Returns the values for the samples of a specificed dynamic data stream in a MGJSON file.

Optionally specify the time span from which to return samples. By default the time for all samples between startTime and endTime in the dynamicdata stream are returned, as defined by the data stream's `samplesTemporalExtent` property in the MGJSON file.

Accepts a single array value to define the path in the hierarchy to the desired dynamic data stream.

The following example returns the values of samples between 1 second and 3 seconds for the first child:

```default
footage("sample.mgjson").dataKeyValues([0], 1, 3)
```

#### Parameters

| `dataPath`   | Array, required. The path in the hierarchy to a static or dynamic data stream.                                   |
|--------------|------------------------------------------------------------------------------------------------------------------|
| `t0`         | Number, optional. The start time, in seconds, of the span from which to return samples. Defaults to `startTime`. |
| `t1`         | Number, optional. The end time, in seconds, of the span from which to return samples. Defaults to `endTime`.     |

#### Type

Array of numbers representing the sample values.
