# Light

**Description**

Light objects have the same attributes and methods as Layer objects, except for:

* `source`
* `effect`
* `mask`
* `width`
* `height`
* `anchorPoint`
* `scale`
* `opacity`
* `audioLevels`
* `timeRemap`
* all the material properties

!!! note
    David Van Brink provides an instructional article and sample project on his [omino pixel blog](http://www.adobe.com/go/learn_ae_ominoflashing) that shows how to use expressions with lights.

---

## Light.pointOfInterest

**Description**

Returns the point of interest values for a light in world space.

**Type**

Array (3-dimensional)

---

## Light.intensity

**Description**

Returns the intensity values of a light as a percentage.

**Type**

Number

---

## Light.color

**Description**

Returns the color value of a light.

**Type**

Array (4-dimensional)

---

## Light.coneAngle

**Description**

Returns the cone angle of a light, in degrees.

**Type**

Number

---

## Light.coneFeather

**Description**

Returns the cone feather value of a light as a percentage.

**Type**

Number

---

## Light.shadowDarkness

**Description**

Returns the shadow darkness value of a light as a percentage.

**Type**

Number

---

## Light.shadowDiffusion

**Description**

Returns the shadow diffusion value of a light, in pixels.

**Type**

Number
