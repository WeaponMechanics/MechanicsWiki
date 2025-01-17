# Flinch

{% hint style="success" %}
Have you purchased [WeaponMechanicsCosmetics](https://www.spigotmc.org/resources/weaponmechanicscosmetics-guns-in-minecraft-1-12-2-1-20-1.104539/)? It is required for this Mechanic to work!
{% endhint %}

The flinch mechanic causes the targeted entity to receive "fake damage," which makes them flash red and shakes their screen.

| Argument         | Description                                                                                                                                  | Default Value |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| `showToEveryone` | Use `false` to only show the effect to the targeted entity. `true` will show the red flash to everyone.                                      | false         |
| `angle`          | The angle where the fake damage is coming from, where 0 is in front of the player, 90 is to the right, 180 is behind, and 270 is to the left | 0.0           |

{% hint style="danger" %}
If you are using a Minecraft server older then 1.19.4, `showToEveryone` will always be true since Spigot added the option in 1.19.4.&#x20;
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Flinch{}"
```

This example causes the source entity to flinch (flash red and screen shake).
{% endtab %}

{% tab title="Example 2" %}
This example is taken from the WeaponMechanics AX-50 config:

```yaml
  Scope:
    Trigger:
      Main_Hand: "LEFT_CLICK"
      Off_Hand: "LEFT_CLICK"
    Zoom_Amount: 1.5
    Shoot_Delay_After_Scope: 16
    Mechanics:
      - "CustomSound{sound=scope.in, volume=0.5, noise=0.1, listeners=Source{}}"
      - "Flinch{}"
    Zoom_Off:
      Mechanics:
        - "CustomSound{sound=scope.out, volume=0.5, noise=0.1, listeners=Source{}}"
        - "Flinch{}"
    Zoom_Stacking:
      Stacks:
        - 4
        - 10
      Mechanics:
        - "CustomSound{sound=scope.in, volume=0.5, noise=0.1}"
        - "Flinch{}"
```

This example causes the player to flinch whenever they scope in/stack/out. If you want a more dramatic screen shake, you can use `repeatInterval` and `repeatAmount` to cause more shaking.&#x20;
{% endtab %}
{% endtabs %}
