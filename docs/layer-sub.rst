Layer Sub-objects
#################

..note::
	For After Effects CC and CS6, the Expression language menu, the "Layer Sub-objects", "Layer General", "Layer Properties", "Layer 3D", and "Layer Space Transforms" have been arranged into a "Layer" submenu.

source
Return type: Comp or Footage. Returns the source Comp or source Footage object for the layer. Default time is adjusted to the time in the source. Example: source.layer(1).position

sourceTime(t = time)
Return type: Number.Returns the layer source corresponding to time t. (After Effects CS5.5 and later.)

effect(name)
Return type: Effect. Argument type: name is a String. After Effects finds the effect by its name in the Effect Controls panel. The name can be the default name or a user-defined name. If multiple effects have the same name, the effect closest to the top of the Effect Controls panel is used. Example:   effect("Fast Blur")("Blurriness")

effect(index)
Return type: Effect. Argument type: index is a Number. After Effects finds the effect by its index in the Effect Controls panel, starting at 1 and counting from the top.

mask(name)
Return type: Mask. Argument type: name is a String. The name can be the default name or a user-defined name. If multiple masks have the same name, the first (topmost) mask is used. Example:   mask("Mask 1")

mask(index)
Return type: Mask. Argument type: index is a Number. After Effects finds the mask by its index in the Timeline panel, starting at 1 and counting from the top.
