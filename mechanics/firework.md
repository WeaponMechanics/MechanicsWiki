# Firework

The firework mechanic spawns a firework rocket, which explodes, generating firework particles. The rocket can be set to explode instantly, creating a firework explosion directly at a location. This is usually used to celebrate an event, such as getting a kill.

| Argument           | Description                                                                                                                                                                                                                   | Default Value                              |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| `effects`          | List of firework effects (see below)                                                                                                                                                                                          | <mark style="color:red;">\*</mark>Required |
| `flightTime`       | The time, in ticks, that the firework should fly upwards before exploding.                                                                                                                                                    | 0 (explode instantly)                      |
| `viewers`          | This is a [#targeter](../#targeter "mention") that defines who can see the firework. Please do not use the `@` symbol; remove it for this. [What is this option?](https://youtu.be/pFsVM4fQNHo)                               | World{}                                    |
| `viewerConditions` | This is a list of conditions that defines who can hear the sound. This is used to create per-player sound effects. Please do not use the `?` symbol; remove it for this. [What is this option?](https://youtu.be/pFsVM4fQNHo) | \[]                                        |

The `effects` argument takes a list of firework effects. When making a list, use square brackets `[]` and separate each value with a comma `,`. Each firework effect has these options:

| Argument    | Description                                                          | Default Value                              | Image                                       |
| ----------- | -------------------------------------------------------------------- | ------------------------------------------ | ------------------------------------------- |
| `shape`     | Choose either `BALL`, `BALL_LARGE`, `BURST`, `CREEPER`, or `STAR`    | BALL                                       | See table below                             |
| `color`     | Either 1 color or a list of colors (like `[ff0000, 00ff00, 0000ff]`) | <mark style="color:red;">\*</mark>Required | ![](../.gitbook/assets/firework.webp)       |
| `fadeColor` | Either 1 color or a list of colors (like `[red, green, blue]`)       | None                                       | no image                                    |
| `trail`     | Use `true` for the particles to have a trail.                        | false                                      | ![](<../.gitbook/assets/firework (1).webp>) |
| `flicker`   | Use `true` to make the particles twinkle as they fade out            | false                                      | ![](<../.gitbook/assets/firework (2).webp>) |

Here are the options for `shape`

{% tabs %}
{% tab title="BALL" %}
![](<../.gitbook/assets/firework (6).webp>)
{% endtab %}

{% tab title="BALL_LARGE" %}
![](<../.gitbook/assets/firework (7).webp>)
{% endtab %}

{% tab title="BURST" %}
![](<../.gitbook/assets/firework (8).webp>)
{% endtab %}

{% tab title="CREEPER" %}
![](<../.gitbook/assets/firework (9).webp>)
{% endtab %}

{% tab title="STAR" %}
![](<../.gitbook/assets/firework (10).webp>)
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Firework{effects=[{color=RED}, {color=GREEN}, {color=BLUE}]}"
  - "Firework{effects=[{color=[RED, GREEN, BLUE]}]}"
  - "Firework{effects=[{color=ff0000}, {color=00ff00}, {color=0000ff}]}"
  - "Firework{effects=[{color=[ff0000, 00ff00, 0000ff]}]}"
```

Each of these 4 lines do the same thing. Each mechanic spawns a ball shaped firework with red, green, and blue particles. The firework explodes instantly on top of the source.&#x20;
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Firework{effects=[{shape=CREEPER, color=GREEN, trail=true, flicker=true}], flightTime=60}"
```

This example spawns a firework that flies for 3 seconds before exploding. The explosion is green, and creeper shaped. The particles have a trail, and twinkle as they fade out.&#x20;
{% endtab %}

{% tab title="Example 3" %}
```yaml
Mechanics:
  - "Firework{effects=[{shape=BALL, color=ff0000}, {shape=STAR, color=ffff00}]}"
```

This exmaple spawns a firework with a red ball effect and a yellow star effect. The firework explodes instantly.&#x20;
{% endtab %}
{% endtabs %}









