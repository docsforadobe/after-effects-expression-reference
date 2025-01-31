# Time Conversion

These methods are all about converting between various time formats.

!!! tip
    If you want more control over the look of timecode in your footage, use the `timeToCurrentFormat()` method or other `timeTo` methods to generate the timecode instead of using the Timecode or Numbers effect.

#### Example

You can easily format and animate the timecode text by creating a text layer, applying whatever text styling you'd like, and adding this expression to the Source Text property:

```js
timeToCurrentFormat();
```

---

## Methods

### framesToTime()

`framesToTime(frames[, fps=1.0 / thisComp.frameDuration])`

#### Description

Returns the time corresponding to the frames argument. It doesn't have to be an integer.

The inverse of [`timeToFrames()`](#timetoframes).

#### Parameters

|    Parameter    |      Type       |                        Description                         |
| --------------- | --------------- | ---------------------------------------------------------- |
| `frames`   | Number   | The amount of frames to convert.
| `fps`        | Number   | Optional. The number of frames per second to use to convert. Defaults to `1.0 / thisComp.frameDuration` (the frame rate of the current composition).

#### Returns

Number

---

### timeToCurrentFormat()

`timeToCurrentFormat([t=time + thisComp.displayStartTime][, fps=1.0 / thisComp.frameDuration][, isDuration=false][, ntscDropFrame=thisComp.ntscDropFrame])`

#### Description

Converts the value of `t` to a String representing time in the current Project Settings display format.

#### Parameters

|    Parameter    |      Type       |                        Description                         |
| --------------- | --------------- | ---------------------------------------------------------- |
| `t`          | Number   | Optional. The time (in seconds) to convert. Defaults to `time + thisComp.displayStartTime`.
| `fps`        | Number   | Optional. Defaults to `1.0 / thisComp.frameDuration` (the frame rate of the current composition).
| `isDuration` | Boolean  | Optional. Whether `t` represents a difference between two times, vs an absolute time. Absolute times are rounded down toward negative infinity; durations are rounded away from zero (up for positive values). Defaults to `false`.
| `ntscDropFrame` | Boolean  | Optional. If `false`, the result is NTSC non-drop-frame timecode. If `true`, the result is NTSC drop-frame timecode. Defaults to `thisComp.ntscDropFrame`.

!!! note
    The `ntscDropFrame` argument was added in After Effects CS5.5.

#### Returns

String

---

### timeToFeetAndFrames()

`timeToFeetAndFrames([t=time + thisComp.displayStartTime][, fps=1.0 / thisComp.frameDuration][, framesPerFoot=16][, isDuration=false])`

#### Description

Converts the value of `t` to a String representing feet of film and frames.

#### Parameters

|    Parameter    |      Type       |                        Description                         |
| --------------- | --------------- | ---------------------------------------------------------- |
| `t`          | Number   | Optional. The time (in seconds) to convert. Defaults to `time + thisComp.displayStartTime`.
| `framesPerFoot` | Number   | Optional. Specifies the number of frames in one foot of film. Defaults to `16` (the most common rate for 35mm footage).
| `isDuration`    | Boolean  | Optional. Whether `t` represents a difference between two times, vs an absolute time. Absolute times are rounded down toward negative infinity; durations are rounded away from zero (up for positive values). Defaults to `false`.

#### Returns

String

---

### timeToFrames()

`timeToFrames([t=time + thisComp.displayStartTime][, fps=1.0 / thisComp.frameDuration][, isDuration=false])`

#### Description

Converts the value of `t` (some amount of time, in seconds) to an integer number of frames.

#### Parameters

|    Parameter    |      Type       |                        Description                         |
| --------------- | --------------- | ---------------------------------------------------------- |
| `t`          | Number   | Optional. The time (in seconds) to convert. Defaults to `time + thisComp.displayStartTime`.
| `fps`        | Number   | Optional. The number of frames per second to use to convert. Defaults to `1.0 / thisComp.frameDuration` (the frame rate of the current composition).
| `isDuration` | Boolean  | Optional. Whether `t` represents a difference between two times, vs an absolute time. Absolute times are rounded down toward negative infinity; durations are rounded away from zero (up for positive values). Defaults to `false`.

#### Returns

Number

---

### timeToNTSCTimecode()

`timeToNTSCTimecode([t=time + thisComp.displayStartTime][, ntscDropFrame=false][, isDuration=false])`

#### Description

Converts `t` to a String representing NTSC timecode.

#### Parameters

|    Parameter    |      Type       |                        Description                         |
| --------------- | --------------- | ---------------------------------------------------------- |
| `t`          | Number   | Optional. The time (in seconds) to convert. Defaults to `time + thisComp.displayStartTime`.
| `ntscDropFrame` | Boolean  | Optional. If `false`, the result is NTSC non-drop-frame timecode. If `true`, the result is NTSC drop-frame timecode. Defaults to `false`.
| `isDuration`    | Boolean  | Optional. Whether `t` represents a difference between two times, vs an absolute time. Absolute times are rounded down toward negative infinity; durations are rounded away from zero (up for positive values). Defaults to `false`.

#### Returns

String

---

### timeToTimecode()

`timeToTimecode([t=time + thisComp.displayStartTime][, timecodeBase=30][, isDuration=false])`

#### Description

Converts the value of `t` to a String representing timecode.

#### Parameters

|    Parameter    |      Type       |                        Description                         |
| --------------- | --------------- | ---------------------------------------------------------- |
| `t`          | Number   | Optional. The time (in seconds) to convert. Defaults to `time + thisComp.displayStartTime`.
| `timecodeBase` | Number   | Optional. Specifies the number of frames in one second. Defaults to `30`.
| `isDuration`   | Boolean  | Optional. Whether `t` represents a difference between two times, vs an absolute time. Absolute times are rounded down toward negative infinity; durations are rounded away from zero (up for positive values). Defaults to `false`.

#### Returns

String
