# Drop Item

{% hint style="info" %}
This mechanic is **different** than the [fake-item.md](fake-item.md "mention") mechanic. Generally, you should instead use the fake item mechanic, which prevents players from picking up items.
{% endhint %}

The drop item mechanic drops a real item on the ground, that players can pick up.&#x20;

| Argument          | Description                                                                                                       | Default Value                              |
| ----------------- | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| `type`            | The [Material](https://app.gitbook.com/s/IIUkVnlH40vVBzLhWWQ8/references#material "mention") to use as the item.  | <mark style="color:red;">\*</mark>Required |
| `customModelData` | The custom model data used to change the item's model.                                                            | None                                       |
| `velocity`        | The velocity to spawn the dropped item with.                                                                      | 0 0 0                                      |

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "DropItem{type=IRON_NUGGET, velocity=r1}"
```

Spawns one iron nugget at the source location, with a subtle random velocity.
{% endtab %}
{% endtabs %}

