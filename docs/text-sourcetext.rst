.. _SourceText:

Source Text
###########

These functions are accessible from :ref:`Text.sourceText` after AE 17.0.

----

.. _SourceText.style:

SourceText.style
****************

**Description**

Returns the text style object for a given ``sourceText`` property.

**Type**

:ref:`TextStyle` object

----

.. _SourceText.getStyleAt:

SourceText.getStyleAt(``charIndex``, ``t = time``)
**************************************************

**Description**

This function returns the style value of a particular character at a specific time.

In case the style is keyframed and changes over time, use the second ``time`` parameter to specify the target time to get the style at.

.. note::
  Using :ref:`SourceText.style` is the same as using ``text.sourceText.getStyleAt(0,0)``

For example, to get the style of the first character at the beginning of the timeline::

  text.sourceText.getStyleAt(0,0);

**Parameters**

========= ==============================================================================================
``index`` Number. The index of the letter or character whose style is needed
``time``  Number, optional. The time within the composition to get the style from. Defaults to ``time``.
========= ==============================================================================================


**Type**

:ref:`TextStyle` object

----

.. _SourceText.createStyle:

SourceText.createStyle()
**************************************************

**Description**

Used to initialize an empty :ref:`TextStyle` object in which you'd manually bake in specific values.

For example, to create a new style with font size 300 and the font Impact::

  text.sourceText.createStyle().setFontSize(300).setFont("Impact");

**Parameters**

None.

**Type**

Empty :ref:`TextStyle` object
