Interpolation
#############

For all the Interpolation methods, the argument t is often time or value, though it can have other values, instead. If t is time, the interpolation between values happens over a duration. If t is value, then the expression maps one range of values to a new range of values.
For additional explanations and examples of the Interpolation methods, see JJ Gifford’s website.
Chris and Trish Meyer provide additional information and examples for these methods in an article on the ProVideo Coalition website.
Ian Haigh provides a script on After Effects Scripts website that you can use to easily apply advanced interpolation method expressions—such as bounces—to properties.
Andrew Devis provides a pair of video tutorials on the Creative COW website that show in detail how to use the linear expression method along with the Convert Audio To Keyframes command.

linear(t, tMin, tMax, value1, value2)
Return type: Number or Array. Argument type: t, tMin, and tMax are Numbers, and value1 and value2 are Numbers or Arrays. Returns value1 when t <= tMin. Returns value2 when t >= tMax. Returns a linear interpolation between value1 and value2 when tMin < t < tMax. For example, this expression on the Opacity property causes Opacity values to ramp linearly from 20% to 80% over the time from 0 seconds to 6 seconds:   linear(time, 0, 6, 20, 80) This method—like all the Interpolation methods—can also be used to convert from one range of values to another. For example, this expression on the Opacity property converts the Opacity values from the range 0%-100% to the range 20%-80%:   linear(value, 0, 100, 20, 80)

linear(t, value1, value2)
Return type: Number or Array. Argument type: t is a Number, and value1 and value2 are Numbers or Arrays. Returns a value that linearly interpolates from value1 to value2 as t ranges from 0 to 1. Returns value1 when t <= 0. Returns value2 when t >= 1.

ease(t, value1, value2)
Return type: Number or Array. Argument type: t is a Number, and value1 and value2 are Numbers or Arrays. Similar to linear with the same arguments, except that the interpolation eases in and out so that the velocity is 0 at the start and end points. This method results in a smooth animation.

ease(t, tMin, tMax, value1, value2)
Return type: Number or Array. Argument type: t, tMin, and tMax are Numbers, and value1 and value2 are Numbers or Arrays. Similar to linear with the same arguments, except that the interpolation eases in and out so that the velocity is 0 at the start and end points. This method results in a smooth animation.

easeIn(t, value1, value2)
Return type: Number or Array. Argument type: t is a Number, and value1 and value2 are Numbers or Arrays. Similar to ease, except that the tangent is 0 only on the value1 side and interpolation is linear on the value2 side.

easeIn(t, tMin, tMax, value1, value2)
Return type: Number or Array. Argument type: t, tMin, and tMax are Numbers, and value1 and value2 are Numbers or Arrays. Similar to ease, except that the tangent is 0 only on the tMin side and interpolation is linear on the tMax side.

easeOut(t, value1, value2)
Return type: Number or Array. Argument type: t is a Number, and value1 and value2 are Numbers or Arrays. Similar to ease, except that the tangent is 0 only on the value2 side and interpolation is linear on the value1 side.

easeOut(t, tMin, tMax, value1, value2)
Return type: Number or Array. Argument type: t, tMin, and tMax are Numbers, and value1 and value2 are Numbers or Arrays. Similar to ease, except that the tangent is 0 only on the tMax side and interpolation is linear on the tMin side.
