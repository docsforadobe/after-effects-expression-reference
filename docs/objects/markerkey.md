# MarkerKey

`thisComp.marker.key(1)`

You can access values for composition markers and layer markers using the same methods. Access layer markers through the thisLayer.marker object; access composition markers through the thisComp.marker object.

For the purpose of expressions, markers are a special type of [Key](./key.md) object, so you can use methods such as [`nearestKey(time)`](./property.md#nearestkey) to access markers, and markers also have `time` and `index` attributes. The `index` attribute is not the number (name) of the marker; it is the keyframe *index* number, representing the order of the marker in the time ruler.

Expressions have access to all the values for a marker that you can set in the Composition Marker or Layer Marker dialog box.

Because the XMP metadata in a footage item can be converted into layer markers for a layer based on that item, expressions can interact with XMP metadata. For information, see [XMP metadata in After Effects](https://helpx.adobe.com/after-effects/using/xmp-metadata.html#xmp_metadata_in_after_effects).

Dan Ebberts provides a tutorial on the [After Effects Developer Center](http://www.adobe.com/devnet/aftereffects/) that includes an example of using XMP metadata with expressions.

!!! info
    On this page, we're going to use `thisComp.marker.key(1)` as a demonstration on how to use these items, however note that any method that returns a [MarkerKey](#) will work.

---

## Attributes

### Marker.chapter

`thisComp.marker.key(1).chapter`

#### Description

Contents of Chapter field in marker dialog box.

#### Type

String

---

### Marker.comment

`thisComp.marker.key(1).comment`

#### Description

Contents of Comment field in marker dialog box.

#### Type

String

---

### Marker.cuePointName

`thisComp.marker.key(1).cuePointName`

#### Description

Contents of cue point Name field in marker dialog box.

#### Type

String

---

### Marker.duration

`thisComp.marker.key(1).duration`

#### Description

Duration, in seconds, of marker.

#### Type

Number

---

### Marker.eventCuePoint

`thisComp.marker.key(1).eventCuePoint`

#### Description

Setting for cue point type in marker dialog box.

`true` for Event; `false` for Navigation.

#### Type

Boolean

---

### Marker.frameTarget

`thisComp.marker.key(1).frameTarget`

#### Description

Contents of Frame Target field in marker dialog box.

#### Type

String

---

### Marker.parameters

`thisComp.marker.key(1).parameters`

#### Description

Contents of Parameter Name and Parameter Value fields in marker dialog box.

#### Type

Associative array of String values

#### Example

If you have a parameter named "background color", then you can use the following expression to access its value at the nearest marker:

```js
thisComp.marker.nearestKey(time).parameters["background color"];
```

---

### Marker.protectedRegion

`thisComp.marker.key(1).protectedRegion`

!!! note
    This functionality was added in After Effects 16.0

#### Description

State of the Protected Region option in the Composition Marker dialog box.

When `true`, the composition marker behaves as a protected region.

Will also return `true` for protected region markers on nested composition layers, but is otherwise not applicable to layer markers.

#### Type

Boolean

---

### Marker.url

`thisComp.marker.key(1).url`

#### Description

Contents of URL field in marker dialog box.

#### Type

String

---

## Example

This expression on the Source Text property of a text layer displays the time, duration, index, comment (name), chapter, URL, frame target, and cue point name for the layer marker nearest the current time, and whether the marker is for an event cue point:

```js
const m = thisLayer.marker.nearestKey(time);
const s = [
    "time:" + timeToCurrentFormat(m.time),
    "duration: " + m.duration,
    "key index: " + m.index,
    "comment:" + m.comment,
    "chapter:" + m.chapter,
    "URL:" + m.url,
    "frame target: " + m.frameTarget,
    "cue point name: " + m.cuePointName,
    "Event cue point? " + m.eventCuePoint,
    ""
];

for (let param in m.parameters){
    s.push("parameter: " + param + " value: " + m.parameters[param]);
}

s.join("\n");
```
