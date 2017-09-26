Vector Math
############

Vector Math functions are global methods that perform operations on arrays, treating them as mathematical vectors. Unlike built-in JavaScript methods, such as Math.sin, these methods are not used with the Math prefix. Unless otherwise specified, Vector Math methods are lenient about dimensions and return a value that is the dimension of the largest input Array object, filling in missing elements with zeros. For example, the expression add([10, 20], [1, 2, 3]) returns [11, 22, 3].

JJ Gifford’s website provides explanations and examples that show how to use simple geometry and trigonometry with expressions.


add(vec1, vec2)
ArrayArgument type: vec1 and vec2 are Arrays. Adds two vectors.

sub(vec1, vec2)
Array Argument type: vec1 and vec2 are Arrays. Subtracts two vectors.

mul(vec, amount)
Array Argument type: vec is an Array, amount is a Number. Multiplies every element of the vector by the amount.

div(vec, amount)
Array Argument type: vec is an Array, amount is a Number. Divides every element of the vector by the amount.

clamp(value, limit1, limit2)
Return type: Number or Array. Argument type: value, limit1, and limit2 are Numbers or Arrays. The value of each component of value is constrained to fall between the values of the corresponding values of limit1 and limit2.

dot(vec1, vec2)
Number Argument type: vec1 and vec2 are Arrays. Returns the dot (inner) product of the vector arguments.

cross(vec1, vec2)
Return type: Array [2 or 3]. Argument type: vec1 and vec2 are Arrays [2 or 3]. Returns the vector cross product of vec1 and vec2. Refer to a math reference or JavaScript guide for more information.

normalize(vec)
Array Argument type: vec is an Array. Normalizes the vector so that its length is 1.0. Using the normalize method is a short way of performing the operation div(vec, length(vec)).

length(vec)
Number Argument type: vec is an Array. Returns the length of vector vec.

length(point1, point2)
Number Argument type: point1 and point2 are Arrays. Returns the distance between two points. The point2 argument is optional. For example, length(point1, point2) is the same as length(sub(point1, point2)).For example, add this expression to the Focus Distance property of a camera to lock the focal plane to the camera's point of interest so that the point of interest is in focus:  length(position, pointOfInterest)

lookAt(fromPoint, atPoint)
Return type: Array [3]. Argument type: fromPoint and atPoint are Arrays [3]. The argument fromPoint is the location in world space of the layer you want to orient. The argument atPoint is the point in world space you want to point the layer at. The return value can be used as an expression for the Orientation property, making the z-axis of the layer point at atPoint. This method is especially useful for cameras and lights. If you use this expression on a camera, turn off auto-orientation. For example, this expression on the Orientation property of a spot light makes the light point at the anchor point of layer number 1 in the same composition: lookAt(position, thisComp.layer(1).position)
