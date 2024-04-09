# Potion

The potion mechanic applies a potion effect to an entity.

| Argument    | Description                                                                                                                                                                                                                        | Default Value                              |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| `potion`    | Which [potion-effects](https://app.gitbook.com/s/IIUkVnlH40vVBzLhWWQ8/references#potion-effects "mention") to use                                                                                                                  | <mark style="color:red;">\*</mark>Required |
| `time`      | The time, in ticks, that the potion will last                                                                                                                                                                                      | 100                                        |
| `level`     | The level, or strength, of the potion effect.                                                                                                                                                                                      | 1                                          |
| `particles` | <p>How to show particles. Use either:<br></p><ul><li><code>HIDE</code> -> Hides all particles</li></ul><ul><li><code>NORMAL</code> -> Shows normal particle</li></ul><ul><li><code>EXTRA</code> -> Shows extra particles</li></ul> | HIDE                                       |
| `hideIcon`  | `true` hides the icon at the top of the player's screen                                                                                                                                                                            | false                                      |

{% hint style="info" %}
To make `FIRE_TICK` deal more damage, you can use [DamageMechanics](https://www.spigotmc.org/resources/damagemechanics.104514/) to multiply the damage.&#x20;
{% endhint %}



{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Potion{potion=POISON} @World{} ?EntityType{entity=PLAYER}"
```

Poisons all players in the current world for 5 seconds.&#x20;
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Potion{potion=STRENGTH, level=2, time=200} @Target{}"
```

Gives the target $$\text{Strength }II$$ for 10 seconds.&#x20;
{% endtab %}
{% endtabs %}



