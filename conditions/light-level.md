# Light Level

The light level condition checks the block light level or skylight level. This means we can check if mobs are spawning in an area.

| Argument | Description                                           | Default Value |
| -------- | ----------------------------------------------------- | ------------- |
| `min`    | The minimum light level                               | 0             |
| `max`    | The maximum light level                               | 15            |
| `mode`   | Either `BLOCK`, `SKY`, or `BOTH` (see below for info) | BOTH          |

{% hint style="info" %}
Mobs can spawn at light level 7 and below
{% endhint %}

{% tabs %}
{% tab title="BLOCK" %}
`BLOCK` only checks light from light sources, such as glowstone, torches, lava, etc.&#x20;
{% endtab %}

{% tab title="SKY" %}
`SKY` only checks the exposure to the sun. This means that your light level will be low if you are underground or under a ceiling.&#x20;
{% endtab %}

{% tab title="BOTH" %}
`BOTH` checks both `BLOCK` and `SKY` and uses whichever value is bigger. This is what Minecraft does to check if mobs can spawn.
{% endtab %}
{% endtabs %}
