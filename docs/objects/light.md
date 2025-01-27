# Light

`thisLayer.lightOption`

This category is for items specific to Light Layers.

Light objects have the same attributes and methods as Layer objects, except for:

- `source`
- `effect`
- `mask`
- `width`
- `height`
- `anchorPoint`
- `scale`
- `opacity`
- `audioLevels`
- `timeRemap`
- all the material properties

!!! note
    David Van Brink provides an instructional article and sample project on his [omino pixel blog](http://www.adobe.com/go/learn_ae_ominoflashing) that shows how to use expressions with lights.

---

## Attributes

---

### Light.castsShadows

`thisLayer.lightOption.castsShadows`

#### Description

Returns whether the light casts shadows.

#### Type

Boolean

---

### Light.color

`thisLayer.lightOption.color`

#### Description

Returns the color value of a light.

#### Type

Array (4-dimensional)

---

### Light.coneAngle

`thisLayer.lightOption.coneAngle`

#### Description

Returns the cone angle of a light, in degrees.

#### Type

Number

---

### Light.coneFeather

`thisLayer.lightOption.coneFeather`

#### Description

Returns the cone feather value of a light as a percentage.

#### Type

Number

---

### Light.falloff

`thisLayer.lightOption.falloff`

#### Description

Returns the cone falloff dropdown option.

#### Type

Number

---

### Light.falloffDistance

`thisLayer.lightOption.falloffDistance`

#### Description

Returns the falloff distance of a light.

#### Type

Number

---

### Light.intensity

`thisLayer.lightOption.intensity`

#### Description

Returns the intensity values of a light as a percentage.

#### Type

Number

---

### Light.pointOfInterest

`thisLayer.lightOption.pointOfInterest`

#### Description

Returns the point of interest values for a light in world space.

#### Type

Array (3-dimensional)

---

### Light.radius

`thisLayer.lightOption.radius`

#### Description

Returns the radius values of a light.

#### Type

Number

---

### Light.shadowDarkness

`thisLayer.lightOption.shadowDarkness`

#### Description

Returns the shadow darkness value of a light as a percentage.

#### Type

Number

---

### Light.shadowDiffusion

`thisLayer.lightOption.shadowDiffusion`

#### Description

Returns the shadow diffusion value of a light, in pixels.

#### Type

Number
