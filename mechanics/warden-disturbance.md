# Warden Disturbance

The warden disturbance mechanic is great for luring the warden toward a location. This uses the same code as Minecraft when you throw a snowball around a warden. This mechanic alerts all wardens in the range that a sound has triggered. This does not increase the Warden's anger level and does not make the warden target players.

| Argument | Description                                                      | Default Value |
| -------- | ---------------------------------------------------------------- | ------------- |
| `range`  | How far away, in blocks, can the wardens hear this disturbance.  | 16.0          |

{% hint style="danger" %}
Be careful not to use this Mechanic too often, the warden may [become confused](https://youtu.be/ncCSkFhSL9k).
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "WardenDisturbance{}"
```

Attracts wardens in a 16 block radius to come investigate the source.
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "WardenDisturbance{range=32} @Target{}"
```

Attracts wardens in a 32-block radius around the target location to go investigate the target. For example, for an explosion, this would cause the warden to investigate the center of the explosion.
{% endtab %}
{% endtabs %}
