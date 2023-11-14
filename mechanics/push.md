# Push

The push mechanic pushes the target entity (or entities) away from the source location. You can use a negative speed to pull entities in. This can create shockwaves or implosions.&#x20;

| Argument             | Description                                                                               | Default Value                              |
| -------------------- | ----------------------------------------------------------------------------------------- | ------------------------------------------ |
| `speed`              | The speed in m/s that the entity be pushed away at. Negative numbers are allowed.         | <mark style="color:red;">\*</mark>Required |
| `verticalMultiplier` | The y speed multiplier. Use `1.0` to move vertically, and `0.0` to cancel vertical speed. | 1.0                                        |

{% hint style="info" %}
If you don't want to boost entities vertically, you should use `verticalMultiplier=0.0`. If you want to throw the target entity in the air, you probably want `verticalMultiplier=1.5`
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Push{speed=5} @World{}"
```

Causes a worldwide shockwave that pushes every entity in the world away from the source location.
{% endtab %}
{% endtabs %}



