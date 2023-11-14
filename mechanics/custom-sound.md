# Custom Sound

The custom sound mechanic can play a named sound from your resource pack. If you want to play a vanilla sound, use the Sound Mechanic instead.

Custom Sounds can be complicated, especially if you create sounds from scratch. Before asking for help in our Discord, please try looking at:

1. The official [sounds.json wiki](https://minecraft.fandom.com/wiki/Sounds.json)
2. The sounds.json file included in the WeaponMechanics resource pack
3. The WeaponMechanics sound file conversion tutorial
4. [Other online tutorials](https://mcmodels.net/how-to-tutorials/resource-pack-tutorials/how-to-add-custom-sounds-to-resource-pack/)
5. [ChatGPT](https://chat.openai.com/) or [Google](https://letmegooglethat.com/?q=Minecraft+sounds.json+tutorial) for help.

| Argument             | Description                                                                                                                                                                                                                                                            | Default Value                              |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| `sound`              | The name of the custom sound to play.                                                                                                                                                                                                                                  | <mark style="color:red;">\*</mark>Required |
| `volume`             | A volume of `0.0` is 0% volume, so nobody will hear it. A volume of `1.0` is 100% so it will be played at full volume. Numbers greater then 1 will not make the sound any louder, it will just make the sound go a further distance (+16 blocks for each +1 to volume) | 1.0                                        |
| `pitch`              | Effects how quickly the sound is played. `0.5` is the lowest pitch. `2.0` is the highest pitch.                                                                                                                                                                        | 1.0                                        |
| `noise`              | Adds a random number to the pitch. This is good for sounds played very often, like gun shots (to make the sounds less repetitive). I recommend a value less then `0.1`                                                                                                 | 0.0                                        |
| `category`           | Defines which [sound settings category](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/SoundCategory.html) is used. This lets players turn down the volume in their settings.                                                                                     | PLAYERS                                    |
| `listeners`          | This is a [#targeter](../#targeter "mention") that defines who can hear the sound. Please do not use the `@` symbol; remove it for this. [What is this option?](https://youtu.be/pFsVM4fQNHo)                                                                          | World{}                                    |
| `listenerConditions` | This is a list of conditions that defines who can hear the sound. This is used to create per-player sound effects. Please do not use the `?` symbol; remove it for this. [What is this option?](https://youtu.be/pFsVM4fQNHo)                                          | \[]                                        |

{% hint style="info" %}
The `sound` argument name will match up precisely with the `/minecraft:playsound` command. Using that command to test your sounds can help you debug.&#x20;
{% endhint %}

Yes, `volume` can be confusing. If you are confused, please look at this chart:

| Volume Value | Volume Percentage | Distance Heard       |
| ------------ | ----------------- | -------------------- |
| `0.1`        | 10%               | 16 blocks            |
| `0.5`        | 50%               | 16 blocks            |
| `1.0`        | 100%              | 16 blocks            |
| `2.0`        | 100%              | 32 blocks (2 chunks) |
| `4.0`        | 100%              | 64 blocks (4 chunks) |

The `listenerConditions` argument takes a list in square brackets `[]` and each condition is separated with a comma. For example, `listenerConditions=[Range{min=20, max=40}, LightLevel{max=8}]`. See the examples below for more information:

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "CustomSound{sound=shoot.ak47.loud}"
```

Plays the `shoot.ak47` sound from the WeaponMechanics resource pack. The sound will be heard by all players up to 96 blocks away.&#x20;

{% hint style="warning" %}
Only players with the resource pack enabled will hear the sound. Anyone without the resource pack will hear nothing.&#x20;
{% endhint %}
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "CustomSound{sound=shoot.ak47close, volume=6, noise=0.05, listenerConditions=[Range{max=40}]}"
  - "CustomSound{sound=shoot.ak47far, volume=6, noise=0.05, listenerConditions=[Range{min=40}]}"
```

Players that are within 40 blocks will hear the `shoot.ak47close` sound. Players outside of this 40 block range will hear the `shoot.ak47far` sound. Since `volume=6`, outside of the 96 block radius (6 chunk radius), players will not hear any sounds.&#x20;

{% hint style="danger" %}
`shoot.ak47close` and `shoot.ak47far` are sounds that I made up for the example. The sounds are not included in the WeaponMechanics resource pack.&#x20;
{% endhint %}
{% endtab %}

{% tab title="Example 3" %}
```yaml
Mechanics:
  - "CustomSound{sound=shoot.ak47.loud, volume=6, noise=0.05, listenerConditions=[MaterialCategory{category=AIR}]}"
  - "CustomSound{sound=shoot.ak47underwater, volume=6, noise=0.05, listenerConditions=[MaterialCategory{category=FLUID}]}"
  - "CustomSound{sound=shoot.ak47indoor, volume=6, noise=0.05, listenerConditions=[MaterialCategory{category=CAVE_AIR}]}"
  - "CustomSound{sound=shoot.ak47narrowhallway, volume=6, noise=0.05, listenerConditions=[MaterialCategory{category=VOID_AIR}]}"
```

This example plays different sounds depending on where the listener is. If they are underwater, they will hear `shoot.ak47underwater` sound.&#x20;

You can use CAVE\_AIR and VOID\_AIR as custom air blocks to customize which sounds players hear in different locations. This powerful tool allows map makers to customize their map with sounds.&#x20;

{% hint style="danger" %}
`shoot.ak47underwater`, `shoot.ak47indoor`, and `shoot.ak47narrowhallway` are sounds that I made up for the example. The sounds are not included in the WeaponMechanics resource pack.&#x20;
{% endhint %}

{% hint style="info" %}
If you want to play indoor sounds, consider using the [light-level.md](../conditions/light-level.md "mention") condition instead.
{% endhint %}
{% endtab %}
{% endtabs %}



