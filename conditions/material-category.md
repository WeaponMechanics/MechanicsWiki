# Material Category

The light level condition checks the block of the targeted location. It can detect different kinds of air, and fluids. This can be used by WeaponMechanics to play underwater muffled sounds.&#x20;

| Argument   | Description                                   | Default Value                              |
| ---------- | --------------------------------------------- | ------------------------------------------ |
| `category` | Which category to use (see below for options) | <mark style="color:red;">\*</mark>Required |

{% tabs %}
{% tab title="AIR" %}
`AIR` allows any non-fluid, non-cave-air, non-void-air block. This is the option that most users should be using.
{% endtab %}

{% tab title="FLUID" %}
`FLUID` checks if the current location is inside of water/lava. In 1.13+, this also checks if you are inside a waterlogged block.&#x20;
{% endtab %}

{% tab title="CAVE_AIR" %}
`CAVE_AIR` checks if the block is a [cave air](https://minecraft.fandom.com/wiki/Air) block.
{% endtab %}

{% tab title="VOID_AIR" %}
`VOID_AIR` checks if the block is a [void air](https://minecraft.fandom.com/wiki/Air) block.
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Sound{sound=ENTITY_ENDERMAN_HURT, pitch=0.5, listenerConditions=[MaterialCategory{category=FLUID}]} @Target{}"
  - "Sound{sound=ENTITY_ENDERMAN_HURT, pitch=2.0, listenerConditions=[MaterialCategory{category=FLUID, inverted=true}]} @Target{}"
```

This example plays the enderman hurt sound at the targeted location. Players who are underwater will hear a very low-pitched sound, but players above water will hear a high-pitched sound.
{% endtab %}
{% endtabs %}
