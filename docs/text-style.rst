.. _TextStyle:

Text Style
##########

These functions are accessible from :ref:`SourceText.style` after AE 17.0.

----

.. _TextStyle.setText:

TextStyle.setText(``value``)
****************************

**Description**

This is used when you want to define (or inherit) a text style, while setting the text content separately.

For example, to inherit the text style and content from another layer::

  const referenceText = thisComp.layer("source layer name").text.sourceText;

  const style = referenceText.getStyleAt(0,0);
  style.setText(referenceText);

Or to create a custom style and then set the text within the expression::

  text.sourceText.createStyle().setFontSize(300).setFont("Impact").setText("Hello world!")

**Parameters**

========= =======================
``value`` String. The text to set
========= =======================

**Type**

None

----

.. _TextStyle.fontSize:

TextStyle.fontSize
******************

**Description**

Returns the value of Font Size for a text layer.

**Type**

Number

----

.. _TextStyle.setFontSize:

TextStyle.setFontSize(``value``)
********************************

**Description**

Used to set the font size to a specified value.

**Parameters**

========= ================================
``value`` Number. The font size to set to.
========= ================================

**Type**

None

----

.. _TextStyle.font:

TextStyle.font
******************

**Description**

Returns the font name for a text layer.

**Type**

String

----

.. _TextStyle.setFont:

TextStyle.setFont(``value``)
********************************

**Description**

Used to set the font to a specified value.

**Parameters**

========= ===========================
``value`` String. The font to set to.
========= ===========================

**Type**

None

----

.. _TextStyle.isFauxBold:

TextStyle.isFauxBold
********************

**Description**

Returns whether faux bold is enabled

**Type**

Boolean

----

.. _TextStyle.setFauxBold:

TextStyle.setFauxBold(``value``)
********************************

**Description**

Used to set the faux bold status

**Parameters**

========= ===============================================
``value`` Boolean. Whether to enable or disable faux bold
========= ===============================================

**Type**

None

----

.. _TextStyle.isFauxItalic:

TextStyle.isFauxItalic
**********************

**Description**

Returns whether faux italic is enabled

**Type**

Boolean

----

.. _TextStyle.setFauxItalic:

TextStyle.setFauxItalic(``value``)
**********************************

**Description**

Used to set the faux italic status

**Parameters**

========= =================================================
``value`` Boolean. Whether to enable or disable faux italic
========= =================================================

**Type**

None

----

.. _TextStyle.isAllCaps:

TextStyle.isAllCaps
*******************

**Description**

Returns whether all caps is enabled

**Type**

Boolean

----

.. _TextStyle.setAllCaps:

TextStyle.setAllCaps(``value``)
*******************************

**Description**

Used to set the All Caps status

**Parameters**

========= ==============================================
``value`` Boolean. Whether to enable or disable all caps
========= ==============================================

**Type**

None

----

.. _TextStyle.isSmallCaps:

TextStyle.isSmallCaps
*********************

**Description**

Returns whether small caps is enabled

**Type**

Boolean

----

.. _TextStyle.setSmallCaps:

TextStyle.setSmallCaps(``value``)
*********************************

**Description**

Used to set the small caps status

**Parameters**

========= ================================================
``value`` Boolean. Whether to enable or disable small caps
========= ================================================

**Type**

None

----

.. _TextStyle.tracking:

TextStyle.tracking
******************

**Description**

Returns the value of Tracking for a text layer.

**Type**

Number

----

.. _TextStyle.setTracking:

TextStyle.setTracking(``value``)
********************************

**Description**

Used to set the tracking to a specified value.

**Parameters**

========= =====================================
``value`` Number. The tracking value to set to.
========= =====================================

**Type**

None

----

.. _TextStyle.leading:

TextStyle.leading
******************

**Description**

Returns the value of leading for a text layer.

**Type**

Number

----

.. _TextStyle.setLeading:

TextStyle.setLeading(``value``)
********************************

**Description**

Used to set the leading to a specified value.

**Parameters**

========= ====================================
``value`` Number. The leading value to set to.
========= ====================================

**Type**

None

----

.. _TextStyle.isAutoLeading:

TextStyle.isAutoLeading
***********************

**Description**

Returns whether auto leading is enabled

**Type**

Boolean

----

.. _TextStyle.setAutoLeading:

TextStyle.setAutoLeading(``value``)
***********************************

**Description**

Used to set the auto leading status

**Parameters**

========= ==================================================
``value`` Boolean. Whether to enable or disable auto leading
========= ==================================================

**Type**

None

----

.. _TextStyle.baselineShift:

TextStyle.baselineShift
***********************

**Description**

Returns the value of baseline shift for a text layer.

**Type**

Number

----

.. _TextStyle.setBaselineShift:

TextStyle.setBaselineShift(``value``)
*************************************

**Description**

Used to set the baseline shift to a specified value.

**Parameters**

========= ===========================================
``value`` Number. The baseline shift value to set to.
========= ===========================================

**Type**

None

----

.. _TextStyle.applyFill:

TextStyle.applyFill
***********************

**Description**

Returns whether text fill color is enabled

**Type**

Boolean

----

.. _TextStyle.setApplyFill:

TextStyle.setApplyFill(``value``)
***********************************

**Description**

Used to set whether text fill is enabled

**Parameters**

========= ================================================
``value`` Boolean. Whether to enable or disable apply fill
========= ================================================

**Type**

None


----

.. _TextStyle.fillColor:

TextStyle.fillColor
***********************

**Description**

Returns the text fill color, RGB values on a scale from 0 - 1.0

**Type**

Array of numbers

----

.. _TextStyle.setFillColor:

TextStyle.setFillColor(``value``)
***********************************

**Description**

Used to set the text fill color

**Parameters**

========= ==================================================================
``value`` Array of numbers. ``[R, G, B]`` with each value between 0.0 to 1.0
========= ==================================================================

**Type**

None

----

.. _TextStyle.applyStroke:

TextStyle.applyStroke
***********************

**Description**

Returns whether text stroke is enabled

**Type**

Boolean

----

.. _TextStyle.setApplyStroke:

TextStyle.setApplyStroke(``value``)
***********************************

**Description**

Used to set whether text stroke is enabled

**Parameters**

========= =================================================
``value`` Boolean. Whether to enable or disable text stroke
========= =================================================

**Type**

None


----

.. _TextStyle.strokeColor:

TextStyle.strokeColor
***********************

**Description**

Returns the text stroke color, RGB values on a scale from 0 - 1.0

**Type**

Array of numbers

----

.. _TextStyle.setStrokeColor:

TextStyle.setStrokeColor(``value``)
***********************************

**Description**

Used to set the text stroke color

**Parameters**

========= ==================================================================
``value`` Array of numbers. ``[R, G, B]`` with each value between 0.0 to 1.0
========= ==================================================================

**Type**

None

----

.. _TextStyle.strokeWidth:

TextStyle.strokeWidth
*********************

**Description**

Returns the stroke width value for a text layer.

**Type**

Number

----

.. _TextStyle.setStrokeWidth:

TextStyle.setStrokeWidth(``value``)
***********************************

**Description**

Used to set the stroke width to a specified value.

**Parameters**

========= =============================================
``value`` Number. The value to set the stroke width to.
========= =============================================

**Type**

None
