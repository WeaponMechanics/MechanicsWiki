# Sculk Shriek

The `SculkShriek{}` mechanic activates nearby [Sculk Shrieker](https://minecraft.fandom.com/wiki/Sculk\_Shrieker) blocks, which causes them to shriek. If there are 4 shrieks for 1 player, a [Warden](https://minecraft.fandom.com/wiki/Warden) will spawn.&#x20;

| Argument       | Description                                                         | Default Value |
| -------------- | ------------------------------------------------------------------- | ------------- |
| `maxBlocks`    | The maximum number of sculk shriekers to activate.                  | 1             |
| `searchRadius` | How far away, in blocks, to search for the nearest catalyst block.  | 8.0           |

{% hint style="danger" %}
When using `SculkShriek{}`, you should always have a Player target. Shriekers can only get mad at players. If no player is targeted, this mechanic will be skipped.&#x20;
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "SculkShriek{}"
```

Finds the nearest shrieker in an 8 block radius and activates it.
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "SculkShriek{searchRadius=24} @Target{}"
```

This finds the sculk shrieker block that is nearest to the **target location** (in a 15 block radius). If the `@Target{}` is a player, then the shrieker will shriek at that player.&#x20;
{% endtab %}
{% endtabs %}
