---
description: Selects all entities in the world
---

# World

The `@World{}` targeter selects all entities in the current world (or the selected world).

| Argument | Description | Default Value     |
| -------- | ----------- | ----------------- |
| `world`  | The world   | The current world |

{% hint style="info" %}
Scatter is _technically_ a [shapes](shapes/ "mention") targeter. This may seem counter-intuitive, but all that means is that `@Scatter{}` can be used in the [particle.md](../mechanics/particle.md "mention") mechanic.
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Command{command=summon creeper <target_x> <target_y> <target_z>, console=true} @World{}"
```

Spawns a Creeper on every entity in the current world. If you want to use this to prank your friends, you might want to add `?EntityType{entity=PLAYER}` to the mechanic. Like this:

```yaml
Mechanics:
  - "Command{command=summon creeper <target_x> <target_y> <target_z>, console=true} @World{} ?EntityType{entity=PLAYER}"
```
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Potion{potion=STRENGTH} @World{world=world_nether}"
```

Applies strength to all entities in the nether.
{% endtab %}
{% endtabs %}

