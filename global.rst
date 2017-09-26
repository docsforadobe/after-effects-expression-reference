Global objects, attributes, and methods (expression reference)

comp(name)
Return type: Comp. Argument type: name is a String. Retrieves another composition by name.

footage(name)
Return type: Footage. Argument type: name is a String. Retrieves a footage item by name.

thisComp
Return type: Comp. Represents the composition containing the expression.

thisLayer
Return type: Layer, Light, or Camera. Represents the layer containing the expression. Because thisLayer is the default object, its use is optional. For example, you can start an expression with thisLayer.width or width and get the same result.

thisProperty
Return type: Property. Represents the property containing the expression. For example, if you write an expression on the Rotation property, you can start an expression with thisProperty to refer to the Rotation property.

time
Return type: Number. Represents the composition time, in seconds, at which the expression is being evaluated.

colorDepth
Return type: Number. Returns the project color depth value. For example, colorDepth returns 16 when the project color depth is 16 bits per channel.

posterizeTime(framesPerSecond)
Return type: Number. Argument type: framesPerSecond is a Number. The framesPerSecond value becomes the frame rate from which the rest of the expression operates. This expression allows you to set the frame rate for a property to be lower than the frame rate of the composition. For example, the following expression updates the property value with a random value once per second:  posterizeTime(1);   random()

value
Return type: Number, Array, or String. Represents the value at the current time for the property containing the expression.
