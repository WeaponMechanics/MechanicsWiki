# Fake Item

{% hint style="success" %}
Have you purchased [WeaponMechanicsCosmetics](https://www.spigotmc.org/resources/weaponmechanicscosmetics-guns-in-minecraft-1-12-2-1-20-1.104539/)? It is required for this Mechanic to work!
{% endhint %}

The fake item mechanic drops a "fake item" on the ground. Fake items are useful, since:

1. They cannot be picked up by players (don't need to worry about players getting illegal items)
2. Has no server performance impact

The Fake Item mechanic can be used for empty shell ejection, blood effects, or any other special effect that benefits from a dropped item.&#x20;

| Argument          | Description                                                                                                       | Default Value                              |
| ----------------- | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| `type`            | The [Material](https://app.gitbook.com/s/IIUkVnlH40vVBzLhWWQ8/references#material "mention") to use as the item.  | <mark style="color:red;">\*</mark>Required |
| `customModelData` | The custom model data used to change the item's model.                                                            | None                                       |
| `time`            | The time, in ticks, before the item disappears.                                                                   | 100                                        |
| `velocity`        | The velocity to spawn the dropped item with.                                                                      | 0 0 0                                      |

{% hint style="warning" %}
If you set the `time` argument too high (>80), players may get confused as to why they cannot pick up items. For example, if you spawn blood items after killing a mob, players may be unable to find the natural mob drops until the fake items despawn.
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "FakeItem{type=IRON_NUGGET, velocity=~-1.1 0.1 0} @Source{eye=true, offset=~-0.12 -0.38 1}"
```

Spawns one iron nugget in front of the eyes of the player. When it spawns, the iron nugget will move to the right (and a little up). This can be used as a bullet shell ejection.
{% endtab %}
{% endtabs %}



