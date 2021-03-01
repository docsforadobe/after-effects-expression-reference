.. _RandomNumbers:

Random Numbers
##############

.. note::
	The wiggle method—which is used to randomly vary a property value—is in the Property attributes and methods category. See Property attributes and methods.

----

.. _seedRandom:

seedRandom(``offset``, ``timeless=false``)
***********************************************

**Description**

The random and gaussRandom methods use a seed value that controls the sequence of numbers. By default, the seed is computed as a function of a unique layer identifier, the property within the layer, the current time, and an offset value of ``0``. Call seedRandom to set the offset to something other than 0 to create a different random sequence. Use true for the timeless argument to not use the current time as input to the random seed. Using true for the timeless argument allows you to generate a random number that doesn’t vary depending on the time of evaluation. The offset value, but not the timeless value, is also used to control the initial value of the wiggle function.

For example, this expression on the Opacity property sets the Opacity value to a random value that does not vary with time::

	seedRandom(123456, true);
	random()*100

The multiplication by ``100`` in this example converts the value in the range ``0–1`` returned by the random method into a ``number`` in the range ``0–100``; this range is more typically useful for the Opacity property, which has values from ``0%`` to ``100%``.

**Parameters**

============ =======
``offset``   Number
``timeless`` Boolean
============ =======

**Type**

None

----

.. _random:

random()
***********************************************

**Description**

Returns a random number in the range ``0–1``.

.. note::
	In After Effects CC and CS6, the behavior of random() is changed to be more random when layer IDs are close together. The wiggle() expression is not affected.

**Type**

Number

----

random(``maxValOrArray``)
***********************************************

**Description**

If ``maxValOrArray`` is a ``Number``, this method returns a number in the range from ``0`` to ``maxValOrArray``. If ``maxValOrArray`` is an ``Array``, this method returns an Array with the same dimension as ``maxValOrArray``, with each component ranging from ``0`` to the corresponding component of ``maxValOrArray``.

**Parameters**

================= ===============
``maxValOrArray`` Number or Array
================= ===============

**Type**

Number or Array

----

random(``minValOrArray``, ``maxValOrArray``)
***********************************************

**Description**

If ``minValOrArray`` and ``maxValOrArray`` are ``Numbers``, this method returns a number in the range from ``minValOrArray`` to ``maxValOrArray``.

If the arguments are ``Arrays``, this method returns an ``Array`` with the same dimension as the argument with the greater dimension, with each component in the range from the corresponding component of ``minValOrArray`` to the corresponding component of ``maxValOrArray``.

For example, the expression ``random([100, 200], [300, 400])`` returns an ``Array`` whose first value is in the range ``100–300`` and whose second value is in the range ``200–400``. If the dimensions of the two input `Arrays` don’t match, higher-dimension values of the shorter Array are filled out with zeros.

**Parameters**

================= ===============
``minValOrArray`` Number or Array
``maxValOrArray`` Number or Array
================= ===============

**Type**

Number or Array

----

.. _gaussRandom:

gaussRandom()
***********************************************

**Description**

The results have a Gaussian (bell-shaped) distribution. Approximately ``90%`` of the results are in the range ``0–1``, and the remaining ``10%`` are outside this range.

**Type**

Number

----

gaussRandom(``maxValOrArray``)
***********************************************

**Description**

When ``maxValOrArray`` is a ``Number``, this method returns a random number. Approximately ``90%`` of the results are in the ``0`` to ``maxValOrArray`` range, and the remaining ``10%`` are outside this range.

When ``maxValOrArray`` is an ``Array``, this method returns an Array of random values, with the same dimension as ``maxValOrArray``. ``90%`` of the values are in the range from ``0`` to ``maxValOrArray``, and the remaining ``10%`` are outside this range.

The results have a Gaussian (bell-shaped) distribution.

**Parameters**

================= ===============
``maxValOrArray`` Number or Array
================= ===============

**Type**

Number or Array

----

gaussRandom(``minValOrArray``, ``maxValOrArray``)
**************************************************

**Description**

If ``minValOrArray`` and ``maxValOrArray`` are ``Numbers``, this method returns a random number. Approximately ``90%`` of the results are in the range from ``minValOrArray`` to ``maxValOrArray``, and the remaining ``10%`` are outside this range.

If the arguments are ``Arrays``, this method returns an ``Array`` of random numbers with the same dimension as the argument with the greater dimension. For each component, approximately ``90%``of the results are in the range from the corresponding component of ``minValOrArray`` to the corresponding component of ``maxValOrArray``, and the remaining ``10%`` are outside this range.

The results have a Gaussian (bell-shaped) distribution.

**Parameters**

================= ===============
``minValOrArray`` Number or Array
``maxValOrArray`` Number or Array
================= ===============

**Type**

Number or Array

----

.. _noise:

noise(``valOrArray``)
***********************************************

**Description**

Returns a number in the range from ``-1`` to ``1``. The noise is not actually random; it is based on Perlin noise, which means that the return values for two input values that are near one another tend to be near one another. This type of noise is useful when you want a sequence of seemingly random numbers that don’t vary wildly from one to the other—as is usually the case when animating any apparently random natural motion.

Example::

	rotation + 360*noise(time)

**Parameters**

============== ========================================
``valOrArray`` Number or an Array (2- or 3-dimensional)
============== ========================================

**Type**

Number
