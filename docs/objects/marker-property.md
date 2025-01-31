# Marker Property

`thisComp.marker`
<br/>
`comp("CompName").marker`
<br/>
`layer("precompName").source.marker`
<br/>
`thisLayer.marker`

The Marker Property is a special version of the [Property](./property.md) object *specifically* for composition & layer markers.

It contains a special version of some of the same attributes and methods as the standard Property object, however most elements are not applicable here.

!!! info
    On this page, we're going to use `thisComp.marker` as a sample on how to call these items, however note that any method that returns a [Marker Property](#) will work.

---

## Attributes

### Marker.numKeys

`thisComp.marker.numKeys`

#### Description

Returns the total number of markers in this composition or layer.

#### Type

Number

---

## Methods

### Marker.key(index)

`thisComp.marker.key(index)`
</br>
`thisComp.marker.key(name)`

#### Description

Returns the [MarkerKey](./markerkey.md) object of the marker with the specified `index` or `name`.

The `index` refers to the order of the marker in composition time, not to the numbered name of the marker.

The `name` value is the name of the marker, as typed in the comment field in the marker dialog box. For example, `marker.key("1")`.

If more than one marker has the same name, this method returns the marker that occurs first in time (in composition or layer time, depending on whether this is a composition or layer marker).

#### Parameters

|     Parameter      |       Type        |                Description                |
| ------------------ | ----------------- | ----------------------------------------- |
| `index`            | Number            | The marker index to get                   |
| `name`<br/>`index` | String<br/>Number | Marker name or index to access marker by. |

#### Type

[MarkerKey](./markerkey.md)

#### Example

Return the time of the first composition marker:

```js
thisComp.marker.key(1).time;
```

Return the time of the layer marker with the name "0":

```js
thisLayer.marker.key("0").time;
```

On a layer, ramp the value of the property from `0` to `100` between two markers identified by name:

```js
const m1 = thisLayr.marker.key("Start").time;
const m2 = thisLayr.marker.key("End").time;
linear(time, m1, m2, 0, 100);
```

---

### Marker.nearestKey()

`thisComp.marker.nearestKey(t)`

#### Description

Returns the marker that is nearest in comp or layer time to the provided time `t`.

#### Parameters

| Parameter |  Type  |               Description                |
| --------- | ------ | ---------------------------------------- |
| `t`       | Number | The time to find the nearest marker from |

#### Returns

[MarkerKey](./markerkey.md)

#### Example

Return the time of the composition marker nearest to the time of 1 second:

```js
thisComp.marker.nearestKey(1).time;
```

This expression returns the time of the layer marker nearest to the current comp time:

```js
thisLayer.marker.nearestKey(time).time;
```
