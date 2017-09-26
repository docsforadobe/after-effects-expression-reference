Color Conversion
################

Harry Frank provides a video tutorial on his `graymachine website <http://www.graymachine.com/tutorials/rgb-to-hsl-expressions/>`_ that shows how to use these color conversion methods to change the color of the waves produced by the Radio Waves effect.

----

rgbToHsl(``rgbaArray``)
***********************
**Description**

Converts a color in RGBA space to HSLA space. The input is an Array of normalized red, green, blue, and alpha channel values, all in the range of 0.0 to 1.0. The resulting value is an Array of hue, saturation, lightness, and alpha channel values, also in the range of 0.0 to 1.0.

Example::

	rgbToHsl.effect("Change Color")("Color To Change")

**Parameters**

============= =====================
``rgbaArray`` Array (4-dimensional)
============= =====================

**Type**

Array (4-dimensional)

----

hslToRgb(``hslaArray``)
***********************
**Description**

Converts a color in HSLA space to RGBA space. This conversion is the opposite of the conversion performed by the rgbToHsl method.

**Parameters**

============= =====================
``hslaArray`` Array (4-dimensional)
============= =====================

**Type**

Array (4-dimensional)
