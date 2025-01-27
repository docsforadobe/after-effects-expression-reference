.. _Global:

Global
######

.. _Global.comp:

comp(``name``)
**************

**Description**

Retrieves another composition by name.

**Parameters**

======== ======
``name`` String
======== ======

**Type**

Comp

----

.. _Global.footage:

footage(``name``)
*****************

**Description**

Retrieves a footage item by name.

**Parameters**

======== ======
``name`` String
======== ======

**Type**

Footage

----

.. _Global.thisProject:

thisProject
***********

**Description**

Represents the project which contains the expression.

**Type**

Project

----

.. _Global.thisComp:

thisComp
********

**Description**

Represents the composition containing the expression.

**Type**

Comp

----

.. _Global.thisLayer:

thisLayer
*********

**Description**

Represents the layer containing the expression. Because thisLayer is the default object, its use is optional. For example, you can start an expression with thisLayer.width or width and get the same result.

**Type**

Layer, Light, or Camera

----

.. _Global.thisProperty:

thisProperty
************

**Description**

Represents the property containing the expression. For example, if you write an expression on the Rotation property, you can start an expression with thisProperty to refer to the Rotation property.

**Type**

Property

----

.. _Global.time:

time
****

**Description**

Represents the composition time, in seconds, at which the expression is being evaluated.

**Type**

Number

----

.. _Global.colorDepth:

colorDepth
**********

**Description**

Type the project color depth value. For example, colorDepth returns ``16`` when the project color depth is 16 bits per channel.

**Type**

Number

----

.. _Global.posterizeTime:

posterizeTime(``updatesPerSecond``)
***********************************

**Description**

This expression allows you to set the frame rate for a property to be lower than the frame rate of the composition.

The ``updatesPerSecond`` value passed in is *the number of times per second* the expression should evaluate.

**Parameters**

====================  ======
``updatesPerSecond``  Number
====================  ======

**Type**

Number

**Examples**

To change a property to a random value 1 time per second::

  posterizeTime(1);

  random()

To change a 2d property (such as Position or Scale) to a random value 3 times per second::

  posterizeTime(3);

  var newValue = random(0, 100);
  [newValue, newValue];

To change a property to a random value within a specified range, every 12 frames::

  var holdFrames = 12;
  var minValue = 50;
  var maxValue = 100;

  posterizeTime(1 / framesToTime(holdFrames));

  var newValue = random(minValue, maxValue);
  newValue;

----

.. _Global.value:

value
*****

**Description**

Represents the value at the current time for the property containing the expression.

**Type**

Number, Array, or String
