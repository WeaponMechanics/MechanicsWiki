# Biome

The biome condition checks whether the target entity/location is in a specific biome.&#x20;

| Argument | Description                 | Default Value                              |
| -------- | --------------------------- | ------------------------------------------ |
| `biome`  | Which biome should we be in | <mark style="color:red;">\*</mark>Required |

Use the [Biome](https://app.gitbook.com/s/IIUkVnlH40vVBzLhWWQ8/references#biome "mention") reference for a full biome list.

Looking for custom biomes from [BiomeManager](https://www.spigotmc.org/resources/biomemanager-custom-biome-colors-and-effects-1-19-4-1-20-1.106419/)? Use [custom-biome.md](custom-biome.md "mention").

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Message{message=You are not in spooky area} @World{} ?Biome{biome=DEEP_DARK, inverted=true}"
```

This sends a message to all players in the current world who are not in the deep dark. This might be used to announce boss events, like: "Join us to fight the Warden"
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Potion{potion=BLINDNESS} ?Biome{biome=DEEP_OCEAN} ?Swimming{}"
```

Gives the source entity blindness if they are underwater in the deep ocean biome.&#x20;
{% endtab %}
{% endtabs %}



