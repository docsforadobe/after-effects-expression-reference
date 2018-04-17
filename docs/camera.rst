Camera
######

Camera objects have the same attributes and methods as Layer objects, except for:

* ``source``
* ``effect``
* ``mask``
* ``width``
* ``height``
* ``anchorPoint``
* ``scale``
* ``opacity``
* ``audioLevels``
* ``timeRemap``
* all the material properties

----

.. _Camera.pointOfInterest:

Camera.pointOfInterest
**********************
**Description**

Returns the point of interest values of a camera in world space.

**Type**

Array (3 dimensional)

----

.. _Camera.zoom:

Camera.zoom
***********
**Description**

Returns the zoom values of a camera in pixels.

Here’s an expression for the Scale property of a layer that maintains the relative size of the layer in frame while changing the z position (depth) of a layer or the Zoom value of a camera::

	cam = thisComp.activeCamera;
	distance = length(sub(position, cam.position));
	scale * distance / cam.zoom;

**Type**

Number

----

.. _Camera.depthOfField:

Camera.depthOfField
*******************
**Description**

Returns ``1`` if the Depth Of Field property of a camera is on, or returns ``0`` if the Depth Of Field property is off.

**Type**

Boolean Number

----

.. _Camera.focusDistance:

Camera.focusDistance
********************
**Description**

Returns the focus distance value of a camera, in pixels.

**Type**

Number

----

.. _Camera.aperture:

Camera.aperture
***************
**Description**

Returns the aperture value of a camera, in pixels.

**Type**

Number

----

.. _Camera.blurLevel:

Camera.blurLevel
****************
**Description**

Returns the blur level value of a camera as a percentage.

**Type**

Number

----

.. _Camera.active:

Camera.active
*************
**Description**

Returns ``true`` if the camera:

#. is the active camera for the composition at the current time: the *video switch* for the camera layer is on
#. the current time is in the range from the *in point* of the camera layer to the *out point* of the camera layer
#. and it is the first (topmost) such camera layer listed in the *timeline panel*

Returns ``false`` otherwise.

**Type**

Boolean
