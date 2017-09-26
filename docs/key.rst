Key
################################################

**Description**

When you access a Key object, you can get time, index, and value properties from it. For example, the following expression gives you the value of the third Position keyframe: position.key(3).value.

The following expression, when written on an Opacity property with keyframes, ignores the keyframe values and uses only the placement of the keyframes in time to determine where a flash should occur::

	d = Math.abs(time - nearestKey(time).time);
	easeOut(d, 0, .1, 100, 0)

----

Key.value
*********************************************
**Description**

Returns the value of the keyframe.

**Type**

Number or Array

----

Key.time
*********************************************
**Description**

Returns the time of the keyframe.

**Type**

Number

----

Key.index
*********************************************
**Description**

Returns the index of the keyframe.

**Type**

Number
