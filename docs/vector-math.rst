Vector Math
############

Vector Math functions are global methods that perform operations on arrays, treating them as mathematical vectors. Unlike built-in JavaScript methods, such as ``Math.sin``, these methods are not used with the Math prefix. Unless otherwise specified, Vector Math methods are lenient about dimensions and return a value that is the dimension of the largest input Array object, filling in missing elements with zeros.

For example, the expression ``add([10, 20], [1, 2, 3])`` returns ``[11, 22, 3]``.

.. note::
	`JJ Gifford’s website <http://www.adobe.com/go/learn_ae_jjgiffordexpressionsgeometrytrig>`_ provides explanations and examples that show how to use simple geometry and trigonometry with expressions.

----

add(``vec1``, ``vec2``)
***************************
**Description**

Adds two vectors.

**Parameters**

======== =====
``vec1`` Array
``vec2`` Array
======== =====

**Type**

Array

----

sub(``vec1``, ``vec2``)
***************************
**Description**

Subtracts two vectors.

**Parameters**

======== =====
``vec1`` Array
``vec2`` Array
======== =====

**Type**

Array

----

mul(``vec``, ``amount``)
***************************
**Description**

Multiplies every element of the vector by the amount.

**Parameters**

========== ======
``vec``    Array
``amount`` Number
========== ======

**Type**

Array

----

div(``vec``, ``amount``)
***************************
**Description**

Divides every element of the vector by the amount.

**Parameters**

========== ======
``vec``    Array
``amount`` Number
========== ======

**Type**

Array

----

clamp(``value``, ``limit1``, ``limit2``)
*****************************************
**Description**

The value of each component of ``value`` is constrained to fall between the values of the corresponding values of ``limit1`` and ``limit2``.

**Parameters**

========== ===============
``value``  Number or Array
``limit1`` Number or Array
``limit2`` Number or Array
========== ===============

**Type**

Number or Array

----

dot(``vec1``, ``vec2``)
***************************
**Description**

Returns the dot (inner) product of the vector arguments.

**Parameters**

======== =====
``vec1`` Array
``vec2`` Array
======== =====

**Type**

Number

----

cross(``vec1``, ``vec2``)
***************************
**Description**

Returns the vector cross product of ``vec1`` and ``vec2``. Refer to a math reference or JavaScript guide for more information.

**Parameters**

======== ===========================
``vec1`` Array (2- or 3-dimensional)
``vec2`` Array (2- or 3-dimensional)
======== ===========================

**Type**

Array (2- or 3-dimensional)

----

normalize(``vec``)
***************************
**Description**

Normalizes the vector so that its length is ``1.0``. Using the normalize method is a short way of performing the operation ``div(vec, length(vec))``.

**Parameters**

======= =====
``vec`` Array
======= =====

**Type**

Array

----

length(``vec``)
***************************
**Description**

Returns the length of vector ``vec``.

**Parameters**

======= =====
``vec`` Array
======= =====

**Type**

Number

----

length(``point1``, ``point2``)
******************************
**Description**

Returns the distance between two points. The ``point2`` argument is optional.

For example, ``length(point1, point2)`` is the same as ``length(sub(point1, point2))``.

For example, add this expression to the Focus Distance property of a camera to lock the focal plane to the camera's point of interest so that the point of interest is in focus::

	length(position, pointOfInterest)

**Parameters**

========== =====
``point1`` Array
``point2`` Array
========== =====

**Type**

Number

----

lookAt(``fromPoint``, ``atPoint``)
***********************************
**Description**

The argument ``fromPoint`` is the location in world space of the layer you want to orient. The argument ``atPoint`` is the point in world space you want to point the layer at. The return value can be used as an expression for the Orientation property, making the z-axis of the layer point at atPoint.

This method is especially useful for cameras and lights. If you use this expression on a camera, turn off auto-orientation.

For example, this expression on the Orientation property of a spot light makes the light point at the anchor point of layer number 1 in the same composition::

	lookAt(position, thisComp.layer(1).position)

**Parameters**

============= =====================
``fromPoint`` Array (3-dimensional)
``atPoint``   Array (3-dimensional)
============= =====================

**Type**

Array (3-dimensional)
