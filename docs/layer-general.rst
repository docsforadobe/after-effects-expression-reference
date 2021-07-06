.. _LayerGeneral:

Layer General
################################################

.. _Layer.width:

Layer.width
*********************************************

**Description**

Returns the width of the layer, in pixels. It is the same as ``source.width``.

**Type**

Number

----

.. _Layer.height:

Layer.height
*********************************************

**Description**

Returns the height of the layer, in pixels. It is the same as ``source.height``.

**Type**

Number

----

.. _Layer.index:

Layer.index
*********************************************

**Description**

Returns the index number of the layer in the composition.

**Type**

Number

----

.. _Layer.parent:

Layer.parent
*********************************************

**Description**

Returns the parent Layer object of the layer, if it has one.

Example::

	position[0] + parent.width

**Type**

Layer, Light, or Camera

----

.. _Layer.hasParent:

Layer.hasParent
*********************************************

**Description**

Returns true if the layer has a parent or false if it doesn't. Use the hasParent attribute to determine if a layer has a parent layer. You can use this attribute even if the layer has no parent layer at present. For example, the following expression indicates that the layer to which you apply it wiggles based on the position of the parent. If the layer has no parent, then it wiggles based on its own position.

If the layer is given a parent later, then the behavior of the layer changes accordingly::

	idx = index;
	if (hasParent) {
		idx = parent.index;
	}
	thisComp.layer(idx).position.wiggle(5,20)

**Type**

Boolean

----

.. _Layer.inPoint:

Layer.inPoint
*********************************************

**Description**

Returns the In point of the layer, in seconds.

.. note::

	In general, the value of outPoint is greater than the value of inPoint. However, if a layer is reversed in time, the value of inPoint is greater than the value of outPoint. Similarly, the value of startTime can be greater than the value of inPoint.

**Type**

Number

----

.. _Layer.outPoint:

Layer.outPoint
*********************************************

**Description**

Returns the Out point of the layer, in seconds.

**Type**

Number

----

.. _Layer.startTime:

Layer.startTime
*********************************************

**Description**

Returns the start time of the layer, in seconds.

**Type**

Number

----

.. _Layer.hasVideo:

Layer.hasVideo
*********************************************

**Description**

Returns ``true`` if the layer has video, or ``false`` if it doesn't.

**Type**

Boolean

----

.. _Layer.hasAudio:

Layer.hasAudio
*********************************************

**Description**

Returns ``true`` if the layer has audio or ``false`` if it doesn't.

**Type**

Boolean

----

.. _Layer.active:

Layer.active
*********************************************

**Description**

Returns ``true`` if the Video switch  is on for the layer and the current time is in the range from the In point of the layer to the Out point of the layer; ``false`` otherwise.

**Type**

Boolean

----

.. _Layer.enabled:

Layer.enabled
*********************************************

**Description**

Returns true if the Video switch  is on for the layer; false otherwise.

**Type**

Boolean

----

.. _Layer.audioActive:

Layer.audioActive
*********************************************

**Description**

Returns true if the Audio switch  is on for the layer and the current time is in the range from the In point of the layer to the Out point of the layer; false otherwise.

**Type**

Boolean

----

.. _Layer.sampleImage:

Layer.sampleImage(``point``, ``radius=[0.5, 0.5]``, ``postEffect=true``, ``t=time``)
**************************************************************************************

**Description**

Samples the color and alpha channel values of a layer and returns the average alpha-weighted value of the pixels within the specified distance of the point as an array: ``[red, green, blue, alpha]``.

If ``postEffect`` is ``true``, the sampled values are for the layer after masks and effects on that layer have been rendered; if ``postEffect`` is ``false``, the sampled values are for the layer before masks and effects have been rendered. The input value point is in layer space; the point ``[0, 0]`` is the center of the upper-left pixel in the layer. The input value ``radius`` specifies the horizontal and vertical distance from the sample center to the edges of the sampled rectangle. The default value samples one pixel.

This example samples a rectangle 4 pixels wide and 3 pixels high, centered around a point 100 pixels down and to the right of the upper-left corner of the layer::

	thisComp.layer(1).sampleImage([100, 100], [2, 1.5])

.. note::
	The postEffect parameter refers to effects applied directly to the layer, not to effects applied indirectly, such as with an adjustment layer.

.. note::
	Using sampleImage in an expression no longer disables multiprocessing.

.. note::
	Dan Ebberts provides an example of how to use the sampleImage method on his MotionScript website.

.. note::
	Todd Kopriva provides instructions for using the sampleImage method and the Point Control effect to monitor colors for a specified point during color correction on his After Effects Region of Interest blog.

**Parameters**

Argument type: point is an Array [2], radius is an Array [2], postEffect is a Boolean, and t is a Number.

**Type**

Array (4-dimensional)
