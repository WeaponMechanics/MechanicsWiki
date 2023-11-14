# Custom Biome

{% hint style="danger" %}
This condition requires [BiomeManager](https://www.spigotmc.org/resources/biomemanager-custom-biome-colors-and-effects-1-19-4-1-20-1.106419/)
{% endhint %}

The custom biome condition checks whether the target entity/location is in a specific biome. This can be used to check for vanilla biomes, but I recommend using the [biome.md](biome.md "mention") condition for vanilla.&#x20;

| Argument | Description                 | Default Value                              |
| -------- | --------------------------- | ------------------------------------------ |
| `biome`  | Which biome should we be in | <mark style="color:red;">\*</mark>Required |

{% tabs %}
{% tab title="Example 1" %}
<pre class="language-yaml"><code class="lang-yaml">Mechanics:
<strong>  - "Potion{potion=POISON, chance=20%} ?CustomBiome(biome=biomemanager:radiation_zone)"
</strong><strong>  - "Potion{potion=WITHER, chance=20%} ?CustomBiome(biome=biomemanager:radiation_zone)"
</strong></code></pre>

This has a 40% chance to give the source entity a negative potion effect (either poison or wither), but they _must_ be in the `biomemanager:radiation_zone` biome.&#x20;
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "CustomSound{sound=city.carnoises} @Source{offset=r40} ?CustomBiome{biome=biomemanager:city}"
```

Plays the named sound `city.carnoises` (this sound is not in any resourcepack, it is just an example sound I made up) in a random direction, 40 blocks away, so long as the source entity is in the city biome.&#x20;
{% endtab %}
{% endtabs %}



