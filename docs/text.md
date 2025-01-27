.. _Text:

Text
####

This category holds generic text-related entries for text layers.

----

.. _Text.sourceText:

Text.sourceText
***************

**Description**

Returns the text content of a text layer.

As of After Effects 17.0, this property returns the :ref:`SourceText` object to access text style properties. If no style properties are specified, this returns the text content as expected.

**Type**

String of text content, or :ref:`SourceText` (AE 17.0+)

----

.. _Text.Font:

Text.Font...
************

**Description**

Launches a dialog window for the user to specify a font name and weight.

Upon selection, the internal font name is injected into the expression editor as a string.

**Type**

String
