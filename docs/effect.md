# Effect

## Effect.active

**Description**

Returns `true` if the effect is turned on (the *effect switch* is selected).

**Type**

Boolean

---

## Effect.param(`name`)

**Description**

Returns a property within an effect. Effect control points are always in layer space.

Example:

```default
effect("Bulge").param("Bulge Height")
```

**Parameters**

| `name`   | String   |
|----------|----------|

**Type**

Property

---

## Effect.param(`index`)

**Description**

Returns a property within an effect. Effect control points are always in layer space. For example, effect(“Bulge”).param(4) returns the Bulge Height property.

**Parameters**

| `index`   | Number   |
|-----------|----------|

**Type**

Property
