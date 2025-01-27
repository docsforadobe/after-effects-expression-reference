# Time Conversion

#### NOTE
If you want more control over the look of timecode in your footage, use the timeToCurrentFormat method or other timeTo methods to generate the timecode instead of using the Timecode or Numbers effect.

Create a text layer, add an expression to the Source Text property, and enter timeToCurrentFormat() in the expression field. With this method, you can format and animate the timecode text. In addition, the timecode uses the same display style defined by the current project settings.

---

## timeToFrames(`t=time + thisComp.displayStartTime`, `fps=1.0 / thisComp.frameDuration`, `isDuration=false`)

**Desciption**

Converts the value of t, which defaults to the current composition time, to an integer number of frames. The number of frames per second is specified in the fps argument, which defaults to the frame rate of the current composition (`1.0 / thisComp.frameDuration`).

The `isDuration` argument, which defaults to `false`, should be `true` if the `t` value represents a difference between two times instead of an absolute time. Absolute times are rounded down toward negative infinity; durations are rounded away from zero (up for positive values).

**Parameters**

| `t`          | Number   |
|--------------|----------|
| `fps`        | Number   |
| `isDuration` | Boolean  |

**Type**

Number

---

## framesToTime(`frames`, `fps=1.0 / thisComp.frameDuration`)

**Desciption**

The inverse of timeToFrames. Returns the time corresponding to the frames argument, which is required. It doesn’t have to be an integer. See timeToFrames for explanation of the `fps` argument.

**Parameters**

| `frames`   | Number   |
|------------|----------|
| `fps`      | Number   |

**Type**

Number

---

## timeToTimecode(`t=time + thisComp.displayStartTime`, `timecodeBase=30`, `isDuration=false`)

**Desciption**

Converts the value of `t` to a String representing timecode. See timeToFrames for an explanation of the `t` and `isDuration` arguments. The `timecodeBase` value, which defaults to `30`, specifies the number of frames in one second.

**Parameters**

| `t`            | Number   |
|----------------|----------|
| `timecodeBase` | Number   |
| `isDuration`   | Boolean  |

**Type**

String

---

## timeToNTSCTimecode(`t=time + thisComp.displayStartTime`, `ntscDropFrame=false`, `isDuration=false`)

**Desciption**

Converts `t` to a `String` representing NTSC timecode. See timeToFrames for an explanation of the `t` and `isDuration` arguments. If `ntscDropFrame` is `false` (the default), the result `String` is NTSC non-drop-frame timecode. If `ntscDropFrame` is `true`, the result `String` is NTSC drop-frame timecode.

**Parameters**

| `t`             | Number   |
|-----------------|----------|
| `ntscDropFrame` | Boolean  |
| `isDuration`    | Boolean  |

**Type**

String

---

## timeToFeetAndFrames(`t=time + thisComp.displayStartTime`, `fps=1.0 / thisComp.frameDuration`, `framesPerFoot=16`, `isDuration=false`)

**Desciption**

Converts the value of `t` to a `String` representing feet of film and frames. See timeToFrames for an explanation of the `t`, `fps`, and `isDuration` arguments. The `framesPerFoot` argument specifies the number of frames in one foot of film. It defaults to `16`, which is the most common rate for 35mm footage.

**Parameters**

| `t`             | Number   |
|-----------------|----------|
| `framesPerFoot` | Number   |
| `isDuration`    | Boolean  |

**Type**

String

---

## timeToCurrentFormat(`t=time + thisComp.displayStartTime`, `fps=1.0 / thisComp.frameDuration`, `isDuration=false`)

**Desciption**

Converts the value of `t` to a `String` representing time in the current Project Settings display format. See timeToFrames for a definition of all the arguments.

#### NOTE
An optional `ntscDropFrame` argument was added to the `timeToCurrentFormat()` function in After Effects CS5.5 and later. Default: `ntscDropFrame=thisComp.ntscDropFrame`.

**Parameters**

| `t`          | Number   |
|--------------|----------|
| `fps`        | Number   |
| `isDuration` | Boolean  |

**Type**

String
