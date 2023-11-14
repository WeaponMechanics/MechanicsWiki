# On Ground

The on ground condition checks if the entity is currently standing on the ground. We can also check which block they are standing on.

| Argument | Description                                        | Default Value                              |
| -------- | -------------------------------------------------- | ------------------------------------------ |
| `blocks` | The list of blocks the entity can be standing on.  | <mark style="color:red;">\*</mark>Required |

{% hint style="info" %}
Using the wildcard (`$`), you can select many blocks at once. For example, `$GLASS` selects all glass blocks and panes. Be careful though, since `$CAR` will select call carpets, and `CARVED_PUMPKIN` and `CARROT`.
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Potion{potion=LEVITATION} @World{} ?OnGround{}"
```

This example will levitate all entities who are standing on the ground in the world.&#x20;
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Potion{potion=LEVITATION} @World{} ?OnGround{blocks=[$GLASS, ICE]}"
```

This example levitates all entities in the world that are standing on glass or ice.&#x20;
{% endtab %}
{% endtabs %}
