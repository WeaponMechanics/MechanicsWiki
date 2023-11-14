# Range

The range condition controls how far away from the source the mechanic can occur. This can be used by WeaponMechanics to control sound dropoff, so sounds further from the source sound further away.&#x20;

| Argument | Description                       | Default Value |
| -------- | --------------------------------- | ------------- |
| `min`    | The minimum distance (in blocks). | 0             |
| `max`    | The maximum distance (in blocks). | None          |

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "CustomSound{sound=shoot.ak47, volume=8, noise=0.05, listenerConditions=[Range{max=40}]}"
  - "CustomSound{sound=shoot.ak47far, volume=8, noise=0.05, listenerConditions=[Range{min=40, max=80}]}"
  - "CustomSound{sound=shoot.ak47veryfar, volume=8, noise=0.05, listenerConditions=[Range{min=80}]}"
```

This example plays the shoot.ak47 sound from the resource pack's [sounds.json](https://minecraft.fandom.com/wiki/Sounds.json). The sound can be heard from the range `[0, 40)` blocks. For players `[40, 80)` blocks away, they hear the `shoot.ak47far` sound instead. For players more than 80 blocks away, they hear the `shoot.ak47veryfar` sound.
{% endtab %}
{% endtabs %}
