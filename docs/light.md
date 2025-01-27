.. _Light:

Light
#####

**Description**

Light objects have the same attributes and methods as Layer objects, except for:

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

.. note::
	David Van Brink provides an instructional article and sample project on his `omino pixel blog <http://www.adobe.com/go/learn_ae_ominoflashing>`_ that shows how to use expressions with lights.

----

.. _Light.pointOfInterest:

Light.pointOfInterest
**********************

**Description**

Returns the point of interest values for a light in world space.

**Type**

Array (3-dimensional)

----

.. _Light.intensity:

Light.intensity
***************

**Description**

Returns the intensity values of a light as a percentage.

**Type**

Number

----

.. _Light.color:

Light.color
*************

**Description**

Returns the color value of a light.

**Type**

Array (4-dimensional)

----

.. _Light.coneAngle:

Light.coneAngle
***************

**Description**

Returns the cone angle of a light, in degrees.

**Type**

Number

----

.. _Light.coneFeather:

Light.coneFeather
*****************

**Description**

Returns the cone feather value of a light as a percentage.

**Type**

Number

----

.. _Light.shadowDarkness:

Light.shadowDarkness
*********************

**Description**

Returns the shadow darkness value of a light as a percentage.

**Type**

Number

----

.. _Light.shadowDiffusion:

Light.shadowDiffusion
*********************

**Description**

Returns the shadow diffusion value of a light, in pixels.

**Type**

Number
