# Lightning

The lightning mechanic strikes lightning at the target location. The lightning bolt will deal damage, turn villagers into witches, etc.

| Argument | Description                                    | Default Value |
| -------- | ---------------------------------------------- | ------------- |
| `effect` | Use `true` for the lightning to deal no damage | false         |

{% hint style="info" %}
To make `LIGHTNING` deal more damage, you can use [DamageMechanics](https://www.spigotmc.org/resources/damagemechanics.104514/) to multiply the damage.&#x20;
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Lightning{} @Scatter{useTarget=false, points=5, horizontalRange=10}"
  - "Lightning{} @Scatter{useTarget=true, points=5, horizontalRange=10} ?EntityType{entity=PLAYER}"
```

Randomly strikes 5 locations in a 10 block radius around the source of the mechanics, and the target. Make sure that the mechanics support the `@Target{}` targeter, since not every section allows it.&#x20;
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Message{message=<white>Zeus: <red>Fear me, mortals} @World{}"
  - "Lightning{repeatAmount=20} @World{}"
```

Warns every player in the world before striking them with lightning 20 times.
{% endtab %}
{% endtabs %}



