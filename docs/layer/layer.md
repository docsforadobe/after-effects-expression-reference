# Layer

As Layers are the foundation of most things in After Effects, this category is large and has been split into smaller pages for various focuses.

These pages reflect the organization of the Expression fly-out menu within After Effects.

!!! info
    Layer is the base class for [Camera](../objects/camera.md) and [Light](../objects/light.md), so Layer attributes and methods are available when working with those layer types (except when noted).

    Layer is also a subclass of [PropertyGroup](../objects/propertygroup.md), so all methods of PropertyGroup, in addition to those listed in the below pages, are available when working with Layer.

Those categories are:

- [Layer Sub-objects](./sub-objects.md) is for items that give you *other objects* based on the current layer; things like the source (for precomps or footage), effects, masks, sourceRect, etc.
- [Layer General](./general.md) holds general info about the layer; width and height, whether the layer has audio or video, the layer's start and end points, etc. With few exceptions, typically *don't change* over the duration of the comp.
- [Layer Properties](./properties.md) is generally for more dynamic properties; the layer's transform data (position, scale, rotation, etc), its audio or time remap, info about markers, and so on.
- [Layer Space Transforms](./layer-space-transforms.md) contains info on how to convert values from one "space" to another, such as from layer space to world space.
- [Layer 3D](./threed.md) is all about the 3d properties of layers. 3d rotation values, material properties, and more live here.
