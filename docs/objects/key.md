# Key

`thisProperty.key(1)`

When you access a Key object, you can get `time`, `index`, and `value` properties from it.

!!! tip
    In expressions, "Key" refers to Keyframes.


!!! info
    On this page, we're going to use `thisProperty.key(1)` as a demonstration on how to use these items, however note that any method that returns a [Key](#) will work.

---

## Attributes

### Key.index

`thisProperty.key(1).index`

#### Description

Returns the index of the keyframe.

#### Type

Number

---

### Key.time

`thisProperty.key(1).time`

#### Description

Returns the time of the keyframe.

#### Type

Number

---

### Key.value

`thisProperty.key(1).value`

#### Description

Returns the value of the keyframe.

#### Type

A value of the same property type as the property being refrenced.

---

## Example

The following expression, when written on an Opacity property with keyframes, ignores the keyframe values and uses only the placement of the keyframes in time to determine where a flash should occur:

```js
const d = Math.abs(time - nearestKey(time).time);
easeOut(d, 0, .1, 100, 0)
```

The following expression gives you the value of the third Position keyframe:

```js
position.key(3).value;
```
