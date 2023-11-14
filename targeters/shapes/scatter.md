---
description: Randomly selects points in a region
---

# Scatter

The `@Scatter{}` targeters randomly selects a certain number of points in a region.

| Argument          | Description                                                                                                                    | Default Value                              |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------ |
| `points`          | The number of points to randomly select.                                                                                       | <mark style="color:red;">\*</mark>Required |
| `horizontalRange` | The horizontal range of the cube.                                                                                              | 5.0                                        |
| `verticalRange`   | The vertical range of the cube.                                                                                                | `horizontalRange`                          |
| `traceDown`       | Use `true` to make the targeted point "fall down" to the ground. Great for targeting points on the ground instead of the air.  | false                                      |

{% hint style="info" %}
Scatter is _technically_ a [.](./ "mention") targeter. This may seem counter-intuitive, but all that means is that `@Scatter{}` can be used in the [particle.md](../../mechanics/particle.md "mention") mechanic.
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Particle{particle=FLAME, shape=Scatter{points=15}}"
  - "Particle{particle=FLAME, count=15, noise=5 5 5}"
```

Both of these mechanics scatter 15 flame particles in a 5x5x5 block cube. _However_, for particles specifically you should always use the second option:

```yaml
Mechanics:
  - "Particle{particle=FLAME, count=15, noise=5 5 5}"
```

Since this example only sends 1 packet to the user (better performance for both the server and the user).&#x20;
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Lightning{} @Scatter{points=3, horizontalRange=10.0, traceDown=true}"
```

Strikes lightning onto the ground in 3 different locations in a 10x10x10 block cube.&#x20;
{% endtab %}
{% endtabs %}
