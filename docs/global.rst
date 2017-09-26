Global
######

----

comp(name)
**********
**Description**

Retrieves another composition by name.

**Parameters**

======== ======
``name`` String
======== ======

**Returns**
Comp

----

footage(name)
*************
**Description**

Retrieves a footage item by name.

**Parameters**

======== ======
``name`` String
======== ======

**Returns**

Footage

----

thisComp
********
**Description**

Represents the composition containing the expression.

**Returns**

Comp

----

thisLayer
*********
**Description**

Represents the layer containing the expression. Because thisLayer is the default object, its use is optional. For example, you can start an expression with thisLayer.width or width and get the same result.

**Returns**

Layer, Light, or Camera

----

thisProperty
************
**Description**

Represents the property containing the expression. For example, if you write an expression on the Rotation property, you can start an expression with thisProperty to refer to the Rotation property.

**Returns**

Property

----

time
****
**Description**

Represents the composition time, in seconds, at which the expression is being evaluated.

**Returns**

Number

----

colorDepth
**********
**Description**

Returns the project color depth value. For example, colorDepth returns 16 when the project color depth is 16 bits per channel.

**Returns**

Number

----

posterizeTime(framesPerSecond)
******************************
**Description**

This expression allows you to set the frame rate for a property to be lower than the frame rate of the composition. For example, the following expression updates the property value with a random value once per second:  posterizeTime(1);   random()

**Parameters**

===================  ======
``framesPerSecond``  Number
===================  ======

The framesPerSecond value becomes the frame rate from which the rest of the expression operates.

**Returns**

Number

----

value
*****
**Description**

Represents the value at the current time for the property containing the expression.

**Returns**

Number, Array, or String
