.. _Comp:

Comp
################################################

.. _Comp.layer:

Comp.layer(``index``)
*********************

**Description**

Retrieves the layer by number (order in the Timeline panel).

Example::

	thisComp.layer(3)

**Parameters**

========= ======
``index`` Number
========= ======

**Type**

Layer, Light, or Camera

----

Comp.layer(``name``)
********************

**Description**

Retrieves the layer by name. Names are matched according to layer name, or source name if there is no layer name. If duplicate names exist, After Effects uses the first (topmost) one in the Timeline panel.

Example::

	thisComp.layer("Solid 1")

**Parameters**

======== ======
``name`` String
======== ======

**Type**

Layer, Light, or Camera

----

Comp.layer(``otherLayer``, ``relIndex``)
****************************************

**Description**

Retrieves the layer that is relIndex layers above or below otherLayer. For example, ``thisComp.layer(thisLayer, 1).active`` returns true if the next layer down in the Timeline panel is active.

**Parameters**

==============  ============
``otherLayer``  Layer Object
==============  ============
``relIndex``  	Number
==============  ============

**Type**

Layer, Light, or Camera

----

.. _Comp.layerByComment:

Comp.layerByComment(``comment``)
********************************

**Description**

Retrieves a layer by matching the comment parameter to the value in the layer's Comment column. The matches are simple text matches. They will match partial words, and are case sensitive. Matching does not appear to use regular expressions or wildcards. If duplicate comments exist, After Effects uses the first (topmost) one in the Timeline panel.

Example::

	thisComp.layerByComment("Control") //note this will match a layer with a comment "Controller" or "Motion Control"

**Parameters**

=========== ======
``comment`` String
=========== ======

**Type**

Layer, Light, or Camera

----

.. _Comp.marker:

Comp.marker
***********

**Description**

.. note::
	You cannot access a composition marker by marker number. If you have a project created in a previous version of After Effects that uses composition marker numbers in expressions, you must change those calls to use marker.key(name) instead. Because the default name of a composition marker is a number, converting the reference to use the name is often just a matter of surrounding the number with quotation marks.

**Type**

MarkerProperty

----

.. _Comp.marker.key:

Comp.marker.key(``index``)
**************************

**Description**

Returns the MarkerKey object of the marker with the specified index. The index refers to the order of the marker in composition time, not to the name of the marker.

For example, this expression returns the time of the first composition marker::

	thisComp.marker.key(1).time

**Parameters**

========= ======
``index`` Number
========= ======

**Type**

MarkerKey

----

Comp.marker.key(``name``)
*************************

**Description**

Returns the MarkerKey object of the marker with the specified name. The name value is the name of the marker, as typed in the comment field in the marker dialog box, for example, marker.key("1"). For a composition marker, the default name is a number. If more than one marker in the composition has the same name, this method returns the marker that occurs first in time (in composition time). The value for a marker key is a String, not a Number.

For example, this expression returns the time of the composition marker with the name "0"::

	thisComp.marker.key("0").time

**Parameters**

======== ======
``name`` String
======== ======

**Type**

MarkerKey

----

.. _Comp.marker.nearestKey:

Comp.marker.nearestKey(``t``)
*****************************

**Description**

Returns the marker that is nearest in time to t.

For example, this expression returns the time of the composition marker nearest to the time of 1 second::

	thisComp.marker.nearestKey(1).time

This expression returns the time of the composition marker nearest to the current time::

	thisComp.marker.nearestKey(time).time

**Parameters**

===== ======
``t`` Number
===== ======

**Type**

MarkerKey

----

.. _Comp.marker.numKeys:

Comp.marker.numKeys
*******************

**Description**

Returns the total number of composition markers in the composition.

**Type**

Number

----

.. _Comp.numLayers:

Comp.numLayers
**************

**Description**

Returns the number of layers in the composition.

**Type**

Number

----

.. _Comp.activeCamera:

Comp.activeCamera
*****************

**Description**

Returns the Camera object for the camera through which the composition is rendered at the current frame. This camera is not necessarily the camera through which you are looking in the Composition panel.

**Type**

Camera

----

.. _Comp.width:

Comp.width
**********

**Description**

Returns the composition width, in pixels.Apply the following expression to the Position property of a layer to center the layer in the composition frame:  [thisComp.width/2, thisComp.height/2]

**Type**

Number

----

.. _Comp.height:

Comp.height
***********

**Description**

Returns the composition height, in pixels.

**Type**

Number

----

.. _Comp.duration:

Comp.duration
*************

**Description**

Returns the composition duration, in seconds.

**Type**

Number

----

.. _Comp.ntscDropFrame:

Comp.ntscDropFrame
******************

**Description**

Returns true if the timecode is in drop-frame format.

.. note::
	Available in After Effects CS5.5 and later.

**Type**

Boolean

----

.. _Comp.displayStartTime:

Comp.displayStartTime
*********************

**Description**

Returns the composition start time, in seconds.

**Type**

Number

----

.. _Comp.frameDuration:

Comp.frameDuration
******************

**Description**

Returns the duration of a frame, in seconds.

**Type**

Number

----

.. _Comp.shutterAngle:

Comp.shutterAngle
*****************

**Description**

Returns the shutter-angle value of the composition, in degrees.

**Type**

Number

----

.. _Comp.shutterPhase:

Comp.shutterPhase
*****************

**Description**

Returns the shutter phase of the composition, in degrees.

**Type**

Number

----

.. _Comp.bgColor:

Comp.bgColor
************

**Description**

Returns the background color of the composition.

**Type**

Array (4-dimensional)

----

.. _Comp.pixelAspect:

Comp.pixelAspect
****************

**Description**

Returns the pixel aspect ratio of the composition.

**Type**

Number

----

.. _Comp.name:

Comp.name
*********

**Description**

Returns the name of the composition.

**Type**

String
