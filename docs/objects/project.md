# Project

`thisProject`

This category holds info related to your current *project* as a whole -- that is, the current AEP. Thus, changing the corresponding project settings will also update the values that these expressions return.

---

## Attributes

### Project.bitsPerChannel

`thisProject.bitsPerChannel`

#### Description

The color depth of the project in bits per channel (bpc), as set in *Project Settings > Color Management*

They are one of 8, 16, or 32. Equivalent to the scripting project attribute [`app.project.bitsPerChannel`](https://ae-scripting.docsforadobe.dev/general/project/#projectbitsperchannel).

#### Type

Number

#### Example

```js
thisProject.bitsPerChannel
```

---

### Project.fullPath

`thisProject.fullPath`

#### Description

The platform-specific absolute file path, including the project file name. If the project has not been saved, it returns an empty string.

#### Type

String

#### Example

```js
thisProject.fullPath
```

---

### Project.linearBlending

`thisProject.linearBlending`

#### Description

The state of the Blend Colors Using 1.0 Gamma option in *Project Settings > Color Management*.

Equivalent to the scripting project attribute [`app.project.linearBlending`](https://ae-scripting.docsforadobe.dev/general/project/#projectlinearblending).

#### Type

Boolean

#### Example

```js
thisProject.linearBlending
```
