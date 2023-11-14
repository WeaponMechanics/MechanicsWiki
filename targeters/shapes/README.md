---
description: Custom shapes for particle effects and other visual effects
---

# Shapes

{% hint style="warning" %}
All shapes (Except [scatter.md](scatter.md "mention")) require WeaponMechanicsCosmetics to be installed!
{% endhint %}

Shapes are used for visual effects. Shapes target a list of points; usually, you spawn one particle at each point. However, since each Shape is still a Targeter, you can use it like any other targeter. For example, this craziness here:

```yaml
Mechanics:
  - "Sound{sound=ENTITY_ENDERMAN_HURT} @Sphere{radius=10, points=10}"
```

This causes 10 enderman sounds to be played, and they will be played evenly spaced on a sphere with a radius of 10 blocks.

* Box
* Circle (2D)
* Lightning&#x20;
* Polygon (2D)
* Sphere
* Spiral
