# Damage

The damage mechanic applies a certain amount of damage to an entity.

| Argument        | Description                                                                                                                                              | Default Value |
| --------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| `damage`        | How much damage to apply                                                                                                                                 | 1.0           |
| `ignoreArmor`   | use `true` to bypass armor damage reductions                                                                                                             | false         |
| `resetCooldown` | Usually, after taking damage, an entity is invulnerable to all damage for half a second. Setting this to `true` takes away these invulnerability ticks.  | false         |

{% hint style="info" %}
1 :heart: in Minecraft is 2 damage. This means a player with 10 :heart: (max health) has 20 health. So you need 20 damage to kill a player.
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Damage{damage=1}"
```

Does half a heart of damage to the entity that caused the mechanics.
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Damage{damage=20, ignoreArmor=true}"
```

Will instantly kill most players/entities, even if they are wearing armor. They can eat a golden apple or similar to prevent themselves from dying.&#x20;
{% endtab %}

{% tab title="Example 3" %}
```yaml
Mechanics:
  - "Damage{damage=20, ignoreArmor=true} @World{}"
```

Will instantly kill most players/entities in the entire world, even if they are wearing armor. They can eat a golden apple or similar to prevent themselves from dying.&#x20;
{% endtab %}
{% endtabs %}



