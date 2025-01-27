# Group

All properties in the Timeline are organized into groups, which share some attributes of properties like `name` and `propertyIndex`. Groups can have a fixed number of properties (e.g. an individual effect whose properties don't change) or a variable number of properties (e.g. the Effects group itself which can have any number of effect within it).

* **Top-level groups in a Layer:**
  : * Motion Trackers
    * Text
    * Contents
    * Masks
    * Effects
    * Transform
    * Layer Styles
    * Geometry Options
    * Material Options
    * Audio
    * Data
    * Essential Properties
* **Nested groups**
  : * Individual effects
    * Individual masks
    * Shape groups
    * Text Animators

---

## numProperties

**Description**

Returns the number of properties or groups directly within a group. This does not include properties nested inside child groups.

!!! TIP
    Find the number of effects applied to a layer with `thisLayer("ADBE Effect Parade").numProperties` using the match name to remain language-agnostic.

**Type**

Number

---

## propertyGroup(`countUp=1`)

**Description**

Returns a higher-level property group relative to the property group on which the method is called. See [propertyGroup(countUp=1)](property.md#property-propertygroup) for additional details.

**Type**

Group

---

## propertyIndex

**Description**

Returns the index of a property group relative to other properties or groups in its property group.

**Type**

Number

---

## name

**Description**

Returns the name of the property group.

**Type**

String
