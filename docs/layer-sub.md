<a id="layersubobjects"></a>

# Layer Sub-objects

#### NOTE
For After Effects CC and CS6, the Expression language menu, the “Layer Sub-objects”, “Layer General”, “Layer Properties”, “Layer 3D”, and “Layer Space Transforms” have been arranged into a “Layer” submenu.

---

<a id="layer-source"></a>

## Layer.source

**Description**

Returns the source Comp or source Footage object for the layer. Default time is adjusted to the time in the source.

Example:

```default
source.layer(1).position
```

**Type**

Comp or Footage

---

<a id="layer-sourcetime"></a>

## Layer.sourceTime(`t=time`)

**Description**

Returns the layer source corresponding to time `t`.

#### NOTE
After Effects CS5.5 and later

**Parameters**

| `t`   | Number   |
|-------|----------|

**Type**

Number

---

<a id="layer-sourcerectattime"></a>

## Layer.sourceRectAtTime(`t = time, includeExtents = false`)

**Description**

Returns a JavaScript object with four attributes: `[top, left, width, height]`

Extents apply only to shape layers and paragraph text layers.

Shape layer extents increase the size of the layer bounds as necessary.

Paragraph text layers returns the bounds of the paragraph box.

#### NOTE
After Effects 13.2 and later.
Paragraph text extents added in After Effects 15.1.

Example:

```default
myTextLayer.sourceRectAtTime().width
```

**Parameters**

| t              | Number   |
|----------------|----------|
| includeExtents | Bool     |

**Type**

Array (4-dimensional)

---

<a id="layer-effect"></a>

## Layer.effect(`name`)

**Description**

After Effects finds the effect by its name in the Effect Controls panel. The name can be the default name or a user-defined name. If multiple effects have the same name, the effect closest to the top of the Effect Controls panel is used.

Example:

```default
effect("Fast Blur")("Blurriness")
```

**Parameters**

| `name`   | String   |
|----------|----------|

**Type**

Effect

---

## Layer.effect(`index`)

**Description**

After Effects finds the effect by its index in the Effect Controls panel, starting at `1` and counting from the top.

**Parameters**

| `index`   | Number   |
|-----------|----------|

**Type**

Effect

---

<a id="layer-mask"></a>

## Layer.mask(`name`)

**Description**

The name can be the default name or a user-defined name. If multiple masks have the same name, the first (topmost) mask is used.

Example:

```default
mask("Mask 1")
```

**Parameters**

| `name`   | String   |
|----------|----------|

**Type**

Mask

---

## Layer.mask(`index`)

**Description**

After Effects finds the mask by its index in the Timeline panel, starting at `1` and counting from the top.

**Parameters**

| `index`   | Number   |
|-----------|----------|

**Type**

Mask
