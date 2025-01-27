.. _TextStyle:

Text Style
##########

Most of these functions are accessible from the :ref:`SourceText.style` object in AE 17.0 and later. Where noted, additional methods were added in AE 25.0. The ability to control per-character styling was also added in 25.0. Use the second and third arguments (when available) to control per-character styling.

.. note::
    When using per-character styling, line breaks and spaces are also considered characters and must be accounted for (or skipped, if desired) when calcuating character indexes.
  
For more info on working with text styles, see:

- `Use Expressions to Edit and Access Text Properties on helpx.adobe.com <https://helpx.adobe.com/after-effects/user-guide.html/after-effects/using/expressions-text-properties.ug.html>`_
- `After Effects 2020: Express Yourself (and Your Text) on blog.adobe.com <https://blog.adobe.com/en/publish/2020/01/24/after-effects-2020-express-yourself-and-your-text>`_

All the methods for :ref:`TextStyle` will return a :ref:`TextStyle` object, so you can call them in a chain, e.g.::

  text.sourceText.style.setFont("Times New Roman").setFontSize(42).setText("New Text");

----

.. _TextStyle.setText:

TextStyle.setText(``value``)
****************************

**Description**

This is used when you want to define (or inherit) a :ref:`TextStyle` while setting the text content separately.

For example, to inherit the style and content from another layer::

  const referenceText = thisComp.layer("Source Layer Name").text.sourceText;

  const style = referenceText.getStyleAt(0,0);
  style.setText(referenceText);

Or to create a custom style and then set the text within the expression::

  text.sourceText.createStyle().setFontSize(300).setFont("Impact").setText("Hello world!");

**Parameters**

========= =======================
``value`` String. The text to set.
========= =======================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.replaceText:

TextStyle.replaceText(``value``, ``startIndex``, ``numOfCharacters``)
*********************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

This is used when you want to define (or inherit) a :ref:`TextStyle`, while setting the content for a substring of the text.

For example, to create a custom style and then set a substring of the text within the expression::

  // assume the value of the source text is "Old Text"
  const referenceText = thisComp.layer("Source Layer Name").text.sourceText;
  const style = referenceText.getStyleAt(0,0);

   // This will change the text from "Old Text" to "NewText" as the first 4 characters are replaced.
  style.replaceText("New", 0, 4);

**Parameters**

==================== ==========================================================
``value``             Required. String. The text to set.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.fontSize:

TextStyle.fontSize
******************

**Description**

Returns the value of Font Size for a Text layer.

**Type**

Number

----

.. _TextStyle.setFontSize:

TextStyle.setFontSize(``value``, ``startIndex``, ``numOfCharacters``)
*********************************************************************

**Description**

Used to set the Font Size to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Number. The Font Size to set.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================


**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.font:

TextStyle.font
**************

**Description**

Returns the font name for a Text layer.

**Type**

String

----

.. _TextStyle.setFont:

TextStyle.setFont(``value``, ``startIndex``, ``numOfCharacters``)
*****************************************************************

**Description**

Used to set the font to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. String. The font to set.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.isFauxBold:

TextStyle.isFauxBold
********************

**Description**

Returns whether Faux Bold is enabled.

**Type**

Boolean

----

.. _TextStyle.setFauxBold:

TextStyle.setFauxBold(``value``, ``startIndex``, ``numOfCharacters``)
*********************************************************************

**Description**

Used to set the Faux Bold status. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Boolean. Whether to enable or disable Faux Bold.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.isFauxItalic:

TextStyle.isFauxItalic
**********************

**Description**

Returns whether Faux Italics are enabled.

**Type**

Boolean

----

.. _TextStyle.setFauxItalic:

TextStyle.setFauxItalic(``value``, ``startIndex``, ``numOfCharacters``)
***********************************************************************

**Description**

Used to set the Faux Italics status. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Boolean. Whether to enable or disable Faux Italics.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.isAllCaps:

TextStyle.isAllCaps
*******************

**Description**

Returns whether All Caps is enabled.

**Type**

Boolean

----

.. _TextStyle.setAllCaps:

TextStyle.setAllCaps(``value``, ``startIndex``, ``numOfCharacters``)
********************************************************************

**Description**

Used to set the All Caps status. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Boolean. Whether to enable or disable All Caps.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.isSmallCaps:

TextStyle.isSmallCaps
**********************

**Description**

Returns whether Small Caps is enabled.

**Type**

Boolean

----

.. _TextStyle.setSmallCaps:

TextStyle.setSmallCaps(``value``, ``startIndex``, ``numOfCharacters``)
**********************************************************************

**Description**

Used to set the Small Caps status. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Boolean. Whether to enable or disable Small Caps.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.tracking:

TextStyle.tracking
******************

**Description**

Returns the value of Tracking for a Text layer.

**Type**

Number

----

.. _TextStyle.setTracking:

TextStyle.setTracking(``value``, ``startIndex``, ``numOfCharacters``)
*********************************************************************

**Description**

Used to set the Tracking to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Number. The Tracking value to set.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.leading:

TextStyle.leading
*****************

**Description**

Returns the value of Leading for a Text layer.

**Type**

Number

----

.. _TextStyle.setLeading:

TextStyle.setLeading(``value``, ``startIndex``, ``numOfCharacters``)
********************************************************************

**Description**

Used to set the Leading to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

Keep in mind that :ref:`TextStyle.isAutoLeading` must be ``false`` in order for `setLeading()` to have any visible affect. You can set Leading to a value other than Auto in the Properties or Character panel, or via :ref:`TextStyle.setAutoLeading`.

**Parameters**

==================== ==========================================================
``value``             Required. Number. The Leading value to set.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.isAutoLeading:

TextStyle.isAutoLeading
***********************

**Description**

Returns whether Auto Leading is enabled.

**Type**

Boolean

----

.. _TextStyle.setAutoLeading:

TextStyle.setAutoLeading(``value``, ``startIndex``, ``numOfCharacters``)
************************************************************************

**Description**

Used to set the Auto Leading status. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Boolean. Whether to enable or disable Auto Leading.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.baselineShift:

TextStyle.baselineShift
***********************

**Description**

Returns the value of Baseline Shift for a Text layer.

**Type**

Number

----

.. _TextStyle.setBaselineShift:

TextStyle.setBaselineShift(``value``, ``startIndex``, ``numOfCharacters``)
**************************************************************************

**Description**

Used to set the Baseline Shift to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Number. The Baseline Shift value to set.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.applyFill:

TextStyle.applyFill
*******************

**Description**

Returns whether Fill Color is enabled.

**Type**

Boolean

----

.. _TextStyle.setApplyFill:

TextStyle.setApplyFill(``value``, ``startIndex``, ``numOfCharacters``)
**********************************************************************

**Description**

Used to set whether Fill Color is enabled. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Boolean. Whether to enable or disable Fill.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.fillColor:

TextStyle.fillColor
***********************

**Description**

Returns the text Fill Color as RGB values on a scale from 0 - 1.0.

**Type**

Array of Numbers.

----

.. _TextStyle.setFillColor:

TextStyle.setFillColor(``value``, ``startIndex``, ``numOfCharacters``)
**********************************************************************

**Description**

Used to set the text Fill Color. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

Keep in mind that :ref:`TextStyle.applyFill` must be ``true`` in order for the fill color to show up. You can set it to ``true`` by enabling Fill in the Properties or Character panel, or by using :ref:`TextStyle.setApplyFill`.

**Parameters**

==================== ==========================================================
``value``             Required. Array of numbers. ``[R, G, B]`` with each value between 0.0 to 1.0.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.applyStroke:

TextStyle.applyStroke
***********************

**Description**

Returns whether Stroke is enabled.

**Type**

Boolean

----

.. _TextStyle.setApplyStroke:

TextStyle.setApplyStroke(``value``, ``startIndex``, ``numOfCharacters``)
************************************************************************

**Description**

Used to set whether Stroke is enabled. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Boolean. Whether to enable or disable Stroke.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.strokeColor:

TextStyle.strokeColor
*********************

**Description**

Returns the Stroke Color as RGB values on a scale from 0 - 1.0.

**Type**

Array of numbers

----

.. _TextStyle.setStrokeColor:

TextStyle.setStrokeColor(``value``, ``startIndex``, ``numOfCharacters``)
************************************************************************

**Description**

Used to set the Stroke Color. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

Keep in mind that :ref:`TextStyle.applyStroke` must be ``true`` and :ref:`TextStyle.strokeWidth` must be greater than zero in order for any stroke color to be shown. You can set these by enabling Stroke or increasing Stroke Width in the Properties or Character panel, or by using :ref:`TextStyle.setApplyStroke` and :ref:`TextStyle.setStrokeWidth`, respectively.

**Parameters**

==================== ==========================================================
``value``             Required. Array of numbers. ``[R, G, B]`` with each value between 0.0 to 1.0.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.strokeWidth:

TextStyle.strokeWidth
*********************

**Description**

Returns the Stroke Width value for a Text layer.

**Type**

Number

----

.. _TextStyle.setStrokeWidth:

TextStyle.setStrokeWidth(``value``, ``startIndex``, ``numOfCharacters``)
************************************************************************

**Description**

Used to set the Stroke Width to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

Keep in mind that :ref:`TextStyle.applyStroke` must be ``true`` in order to see any change in stroke width. You can set this either by enabling Stroke in the Properties or Character panel, or via :ref:`TextStyle.setApplyStroke`.

**Parameters**

==================== ==========================================================
``value``             Required. Number. The value to set the Stroke Width.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.


----

.. _TextStyle.kerningType:

TextStyle.kerningType
*********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the Kerning Type for a Text layer.


.. _ReturnedKerningType:

**Type**

Predefined string as defined in `ReturnedKerningType`_. Read-only. One of the following:

- ``manual``
- ``metrics``
- ``optical``

----

.. _TextStyle.setKerningType:

TextStyle.setKerningType(``value``, ``startIndex``, ``numOfCharacters``)
*****************************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to set the Kerning Type. The value will be applied to the entire Text layer unless a start index and number of characters are specified.
Please note that ``manual`` is not a valid value for this method. To set manual kerning, use :ref:`TextStyle.setKerning`.
Also, please note that automatic kerning will take a precendence over manual kerning.

.. _KerningType:

**Type**

Predefined string as defined in `KerningType`_. One of the following:

- ``metrics``
- ``optical``
  

**Parameters**

==================== ==========================================================
``value``             Required. Predefined string as defined in `KerningType`_. The value to set for Kerning Type.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be changed. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Type**

None

----

.. _TextStyle.kerning:

TextStyle.kerning
**********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the Kerning Value for a Text Layer. For this value to be returned as anything other than zero, the `KerningType`_ must not be set.

**Type**

Number. Read-only.

----

.. _TextStyle.setKerning:

TextStyle.setKerning(``value``, ``characterIndex``)
**********************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to set the Kerning Value at the specifed character index. This will only affect the Text layer when `KerningType`_ is not set for the character index.

**Parameters**

==================== ==========================================================
``value``             Required. Number. The value to set the Kerning Value.
``characterIndex``    Required. Number. The character index for the substring to be applied.
==================== ==========================================================

**Type**

None

----

.. _TextStyle.tsume:

TextStyle.tsume
***************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the Tsume value for a Text layer.

**Type**

Number (between 0 and 1).

----

.. _TextStyle.setTsume:

TextStyle.setTsume(``value``, ``startIndex``, ``numOfCharacters``)
******************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to set the Tsume to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Number (between 0 and 100). The value to set the Tsume.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Type**

None

----

.. _TextStyle.verticalScaling:

TextStyle.verticalScaling
*************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the Vertical Scaling for a Text layer.

**Type**

Number

----

.. _TextStyle.setVerticalScaling:

TextStyle.setVerticalScaling(``value``, ``startIndex``, ``numOfCharacters``)
****************************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to set the Vertical Scaling to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Number. The value to set the Vertical Scaling.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.horizontalScaling:

TextStyle.horizontalScaling
***************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the Horizontal Scaling for a Text layer.

**Type**

Number

----

.. _TextStyle.setHorizontalScaling:

TextStyle.setHorizontalScaling(``value``, ``startIndex``, ``numOfCharacters``)
******************************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to set the Horizontal Scaling to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Number. The value to set the Horizontal Scaling.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.lineJoin:

TextStyle.lineJoin
*******************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the Line Join Type for a Text layer. The returned value is a defined string in `LineJoinType`_.

.. _LineJoinType:

**Type**

Predefined string as defined in `LineJoinType`_. One of the following:

- ``bevel``
- ``miter``
- ``round``

----

.. _TextStyle.setLineJoin:

TextStyle.setLineJoin(``value``, ``startIndex``, ``numOfCharacters``)
*********************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to set the Line Join Type to a specified value. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Predefined string as defined in `LineJoinType`_. The value to set for Line Join Type.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.baselineOption:

TextStyle.baselineOption
*************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the Baseline Option Type for a Text layer. The returned value is a defined string in BaselineOptionType_.

.. _BaselineOptionType:

**Type**

Predefined string as defined in BaselineOptionType_. One of the following:

- ``default``
- ``subscript``
- ``superscript``

----

.. _TextStyle.setBaselineOption:

TextStyle.setBaselineOption(``value``, ``startIndex``, ``numOfCharacters``)
***************************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to set the baseline option to a specified predefined string. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Predefined string as defined in BaselineOptionType_ . The value to set for Baseline Option.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.digitSet:

TextStyle.digitSet
*******************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the Digit Set for a Text layer. The returned value is a defined string in DigitSetType_.

.. _DigitSetType:

**Type**

Predefined string as defined in DigitSetType_. One of the following:

- ``default``
- ``hindidigits``

----

.. _TextStyle.setDigitSet:

TextStyle.setDigitSet(``value``, ``startIndex``, ``numOfCharacters``)
*********************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to set the Digit Set to a specified predefined string. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Predefined string as defined in DigitSetType_ . The value to use for Digit Set.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.isLigature:

TextStyle.isLigature
*********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns whether ligatures are enabled.

**Type**

Boolean

----

.. _TextStyle.setLigature:

TextStyle.setLigature(``value``, ``startIndex``, ``numOfCharacters``)
*********************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to enable or disable ligatures. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Boolean. Whether to enable or disable ligatures.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.baselineDirection:

TextStyle.baselineDirection
****************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the Baseline Direction for a Text layer. The returned value is a defined string in BaselineDirectionType_.

.. _BaselineDirectionType:

**Type**

Predefined string as defined in BaselineDirectionType_. One of the following:

- ``default``
- ``rotated``
- ``tate-chuu-yoko``

----

.. _TextStyle.setBaselineDirection:

TextStyle.setBaselineDirection(``value``, ``startIndex``, ``numOfCharacters``)
******************************************************************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Used to set the Baseline Direction to a specified predefined string. The value will be set for the entire Text layer unless ``startIndex`` and ``numOfCharacters`` are specified.

**Parameters**

==================== ==========================================================
``value``             Required. Predefined string as defined in BaselineDirectionType_ . The value to set for Baseline Direction.
``startIndex``        Optional. Number. The start index for the substring to be replaced. Defaults to 0.
``numOfCharacters``   Optional. Number. The length of the substring to be replaced. Defaults to the number of characters until end of the string.
==================== ==========================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.justification:

TextStyle.justification
************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the value of Justification of the first paragraph of a Text layer.

.. warning::
    The left and right values for alignment/justification will be reversed if the Text layer's :ref:`TextStyle.direction` is set to use `right-to-left`. You can control this using the Property or Paragraph panel, or via :ref:`TextStyle.setDirection`.

.. _JustificationType:

**Type**

Predefined string as defined in JustificationType_. One of the following:

- ``alignCenter``
- ``alignLeft``
- ``alignRight``
- ``justifyFull``
- ``justifyLastCenter``
- ``justifyLastLeft``
- ``justifyLastRight``

----

.. _TextStyle.setJustification:

TextStyle.setJustification(``value``)
***************************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to set the Justification for the entire Text layer.

.. warning::
    The left and right values for alignment/justification will be reversed if the Text layer's :ref:`TextStyle.direction` is set to use `right-to-left`. You can control this using the Property or Paragraph panel, or via :ref:`TextStyle.setDirection`.

**Parameters**

================== ======================================================================================================================================================
``value``           Predefined string as defined in JustificationType_; the desired value for the Justification.
================== ======================================================================================================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.direction:

TextStyle.direction
*********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the value of Direction of the first paragraph of a Text layer. 

.. _DirectionType:

**Type**

Predefined string as defined in DirectionType_. One of the following:

- ``left-to-right``
- ``right-to-left``

----

.. _TextStyle.setDirection:

TextStyle.setDirection(``value``)
***********************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to set the Direction for the entire Text layer, either ``left-to-right`` or ``right-to-left``.

**Parameters**

================== ======================================================================================================================================================
``value``            Predefined string as defined in DirectionType_; the desired value for Direction.
================== ======================================================================================================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.leftMargin:

TextStyle.leftMargin
**********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the value of Left Margin of the first paragraph of a Text layer. 

**Type**

Number

----

.. _TextStyle.setLeftMargin:

TextStyle.setLeftMargin(``value``)
************************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to set the Left Margin of a Text layer to a specified value.

**Parameters**

================== ===========================================================================
``value``            Number; the desired value for Left Margin.
================== ===========================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.rightMargin:

TextStyle.rightMargin
***********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the value of Right Margin of the first paragraph of a Text layer.

**Type**

Number

----

.. _TextStyle.setRightMargin:

TextStyle.setRightMargin(``value``)
************************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to set the Right Margin of a Text layer to a specified value.

**Parameters**

================== ===========================================================================
``value``            Number; the desired value for Right Margin.
================== ===========================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.spaceAfter:

TextStyle.spaceAfter
**********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the value of the Space After the first paragraph of a Text layer.

**Type**

Number

----

.. _TextStyle.setSpaceAfter:

TextStyle.setSpaceAfter(``value``)
************************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to set the Space After attribute of a Text layer to a specified value.

**Parameters**

================== ===========================================================================
``value``            Number; the desired value for the Space After attribute.
================== ===========================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.spaceBefore:

TextStyle.spaceBefore
***********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the value of the Space Before the first paragraph of a Text layer.

**Type**

Number

----

.. _TextStyle.setSpaceBefore:

TextStyle.setSpaceBefore(``value``)
*************************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to set the Space Before attribute of a Text layer to a specified value.

**Parameters**

================== ===========================================================================
``value``            Number; the desired value for the Space Before attribute.
================== ===========================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.firstLineIndent:

TextStyle.firstLineIndent
***************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the value of First Line Indent of the first line of the first paragraph of a Text layer.

**Type**

Number

----

.. _TextStyle.setFirstLineIndent:

TextStyle.setFirstLineIndent(``value``)
*****************************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to set the First Line Indent of a Text layer to a specified value.

**Parameters**

================== ===========================================================================
``value``            Number; the desired value for First Line Indent.
================== ===========================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.isEveryLineComposer:

TextStyle.isEveryLineComposer
*******************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns ```true``` if the Text layer if Every-Line Composer is set for the first paragraph of a Text layer and ```false``` if Single-Line Composer is set for the first paragraph of a Text layer

**Type**

Boolean

----

.. _TextStyle.setEveryLineComposer:

TextStyle.setEveryLineComposer(``value``)
*******************************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to enable or disable the Every-Line Composer for the entire Text layer.

**Parameters**

================== ======================================================================================================================================================
``value``            Boolean. Whether to enable or disable Every-Line Composer.
================== ======================================================================================================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.isHangingRoman:

TextStyle.isHangingRoman
**************************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Whether Hanging Roman Punctuation is set for the entire Text layer. 

**Type**

Boolean

----

.. _TextStyle.setHangingRoman:

TextStyle.setHangingRoman(``value``)
**************************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to enable or disable Hanging Roman Punctuation for the entire Text layer.

**Parameters**

================== ======================================================================================================================================================
``value``            Boolean. Whether to enable or disable Roman Hanging Punctuation.
================== ======================================================================================================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

----

.. _TextStyle.leadingType:

TextStyle.leadingType
***********************

.. note::
  This functionality was added in After Effects 25.0.

**Description**

Returns the value of Leading Type for the first paragraph of a Text layer.

.. _LeadingType:

**Type**

Predefined string as defined in LeadingType_. One of the following:

- ``bottom-to-bottom``
- ``top-to-top``

----

.. _TextStyle.setLeadingType:

TextStyle.setLeadingType(``value``)
*************************************

.. note::
  This functionality was added in After Effects 25.0.

.. warning::
  This method must be called after :ref:`TextStyle.setText` if both are being used.

**Description**

Used to set the Leading Type for the entire Text layer.



**Parameters**

================== ======================================================================================================================================================
``value``            Predefined string as defined in LeadingType_; the desired value for Leading Type.
================== ======================================================================================================================================================

**Returns**

A :ref:`TextStyle object <TextStyle>`.

