# Ignite

The ignite mechanic lights an entity on fire and does damage over time.

| Argument | Description                                                      | Default Value |
| -------- | ---------------------------------------------------------------- | ------------- |
| `time`   | How long (in ticks) the fire should last (20 ticks = 1 second).  | 100           |

{% hint style="info" %}
To make `FIRE_TICK` deal more damage, you can use [DamageMechanics](https://www.spigotmc.org/resources/damagemechanics.104514/) to multiply the damage.&#x20;
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Ignite{time=200}"
```

Lights the source entity on fire for 10 seconds.
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Ignite{} @World{} ?EntityType{entity=ZOMBIE}"
```

Lights all zombies in the world on fire.
{% endtab %}
{% endtabs %}



