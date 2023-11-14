# Leap

The leap mechanic causes the source entity to be pushed toward the target location. You can use a negative speed to leap away from the target location. This can create weapon recoil, rocket jumps, jetpacks, implosions, and explosions (and more).

| Argument             | Description                                                                               | Default Value                              |
| -------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------ |
| `speed`              | The speed in m/s that the entity should leap at. Negative numbers are allowed.            | <mark style="color:red;">\*</mark>Required |
| `verticalMultiplier` | The y speed multiplier. Use `1.0` to move vertically, and `0.0` to cancel vertical speed. | 1.0                                        |

{% hint style="info" %}
When using weapon recoil, you probably want `verticalMultiplier=0.0`, but for a jetpack, you probably want `verticalMultiplier=1.5`
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Leap{speed=5} @Source{offset=~0 1 1}"
```

Causes the source entity to fly forwards and upwards.
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Leap{speed=10}"
```

This example quickly pushes the source entity towards the target.
{% endtab %}
{% endtabs %}



