.. _LayerSubObjects:

Layer Sub-objects
#################

.. note::
	For After Effects CC and CS6, the Expression language menu, the "Layer Sub-objects", "Layer General", "Layer Properties", "Layer 3D", and "Layer Space Transforms" have been arranged into a "Layer" submenu.

----

.. _Layer.source:

Layer.source
*********************

**Description**

Returns the source Comp or source Footage object for the layer. Default time is adjusted to the time in the source.

Example::

	source.layer(1).position

**Type**

Comp or Footage

----

.. _Layer.sourceTime:

Layer.sourceTime(``t=time``)
******************************

**Description**

Returns the layer source corresponding to time ``t``.

.. note::
	After Effects CS5.5 and later

**Parameters**

===== ======
``t`` Number
===== ======

**Type**

Number

----

.. _Layer.sourceRectAtTime:

Layer.sourceRectAtTime(``t = time, includeExtents = false``)
************************************************************

**Description**

Returns a JavaScript object with four attributes: ``[top, left, width, height]``

Extents apply only to shape layers and paragraph text layers.

Shape layer extents increase the size of the layer bounds as necessary.

Paragraph text layers returns the bounds of the paragraph box.

.. note::
  After Effects 13.2 and later.
  Paragraph text extents added in After Effects 15.1.

Example::

  myTextLayer.sourceRectAtTime().width

**Parameters**

================ ======
`t`              Number
`includeExtents` Bool
================ ======

**Type**

Array (4-dimensional)

----

.. _Layer.effect:

Layer.effect(``name``)
**********************

**Description**

After Effects finds the effect by its name in the Effect Controls panel. The name can be the default name or a user-defined name. If multiple effects have the same name, the effect closest to the top of the Effect Controls panel is used.

Example::

	effect("Fast Blur")("Blurriness")

**Parameters**

======== ======
``name`` String
======== ======

**Type**

Effect

----

Layer.effect(``index``)
***********************

**Description**

After Effects finds the effect by its index in the Effect Controls panel, starting at ``1`` and counting from the top.

**Parameters**

========= ======
``index`` Number
========= ======

**Type**

Effect

----

.. _Layer.mask:

Layer.mask(``name``)
*********************

**Description**

The name can be the default name or a user-defined name. If multiple masks have the same name, the first (topmost) mask is used.

Example::

	mask("Mask 1")

**Parameters**

======== ======
``name`` String
======== ======

**Type**

Mask

----

Layer.mask(``index``)
*********************

**Description**

After Effects finds the mask by its index in the Timeline panel, starting at ``1`` and counting from the top.

**Parameters**

========= ======
``index`` Number
========= ======

**Type**

Mask
