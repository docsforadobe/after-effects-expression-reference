.. _SourceText:

Source Text
###########

These functions are accessible on the :ref:`Text.sourceText` object in AE 17.0 and later.

----

.. _SourceText.style:

SourceText.style
****************

**Description**

Returns the :ref:`TextStyle` object for a given ``sourceText`` property.

**Type**

:ref:`TextStyle` object

----

.. _SourceText.getStyleAt:

SourceText.getStyleAt(``charIndex``, ``t = time``)
**************************************************

**Description**

This function returns the :ref:`TextStyle` object of a particular character at a specific time.

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
*************************

**Description**

Used to initialize an empty :ref:`TextStyle` object in which you'd manually bake in specific values.

For example, to create a new style with font size 300 and the font Impact::

  text.sourceText.createStyle().setFontSize(300).setFont("Impact");

**Parameters**

None.

**Type**

Empty :ref:`TextStyle` object.

----

.. _SourceText.isVerticalText:

SourceText.isVerticalText
**************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns ``true`` if the Text layer is vertical and ``false`` if it is horizontal.

**Parameters**

None.

**Type**

Boolean

----

.. _SourceText.isHorizontalText:

SourceText.isHorizontalText
****************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns ``true`` if the Text layer is horizontal and ``false`` if it is vertical.

**Parameters**

None.

**Type**

Boolean

----

.. _SourceText.isPointText:

SourceText.isPointText
***********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns ``true`` if a Text layer is Point text. If the Text layer is Paragraph text, it returns ``false``.

**Parameters**

None.

**Type**

Boolean

----

.. _SourceText.isParagraphText:

SourceText.isParagraphText
***************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns ``true`` if a Text layer is Paragraph text. If the Text layer is a Point text, it returns ``false``.

**Parameters**

None.

**Type**

Boolean

