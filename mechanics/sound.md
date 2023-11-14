# Sound

Plays a vanilla sound for nearby players. If you want to play a sound from a resource pack, use [custom-sound.md](custom-sound.md "mention") instead.

<table><thead><tr><th>Argument</th><th width="392.3333333333333">Description</th><th>Default Value</th></tr></thead><tbody><tr><td><code>sound</code></td><td>The <a data-mention href="http://127.0.0.1:5000/s/IIUkVnlH40vVBzLhWWQ8/references#sound">Sound</a> to play.</td><td><mark style="color:red;">*</mark>Required</td></tr><tr><td><code>volume</code></td><td>A volume of <code>0.0</code> is 0% volume, so nobody will hear it. A volume of <code>1.0</code> is 100% so it will be played at full volume. Numbers greater then 1 will not make the sound any louder, it will just make the sound go a further distance (+16 blocks for each +1 to volume)</td><td>1.0</td></tr><tr><td><code>pitch</code></td><td>Effects how quickly the sound is played. <code>0.5</code> is the lowest pitch. <code>2.0</code> is the highest pitch.</td><td>1.0</td></tr><tr><td><code>noise</code></td><td>Adds a random number to the pitch. This is good for sounds played very often, like gun shots (to make the sounds less repetitive). I recommend a value less then <code>0.1</code> </td><td>0.0</td></tr><tr><td><code>category</code></td><td>Defines which <a href="https://hub.spigotmc.org/javadocs/spigot/org/bukkit/SoundCategory.html">sound settings category</a> is used. This lets players turn down the volume in their settings.</td><td>PLAYERS</td></tr><tr><td><code>listeners</code></td><td>This is a <a data-mention href="../#targeter">#targeter</a> that defines who can hear the sound. Please do not use the <code>@</code> symbol; remove it for this. <a href="https://youtu.be/pFsVM4fQNHo">What is this option?</a></td><td>World{}</td></tr><tr><td><code>listenerConditions</code></td><td>This is a list of conditions that defines who can hear the sound. This is used to create per-player sound effects. Please do not use the <code>?</code> symbol; remove it for this. <a href="https://youtu.be/pFsVM4fQNHo">What is this option?</a></td><td>[]</td></tr></tbody></table>

{% hint style="warning" %}
The `/minecraft:playsound` command sound names will _NOT_ match exactly with sounds here. Replace all dots (`.`) with underscores. Use the correct list for your version: [Sound](http://127.0.0.1:5000/s/IIUkVnlH40vVBzLhWWQ8/references#sound "mention")
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
  - "Sound{sound=ENTITY_ENDERMAN_HURT}"
```

Plays the enderman hurt sound at the source location for all players within 16 blocks to hear.&#x20;
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Sound{sound=ENTITY_ENDERMAN_HURT, noise=0.1, category=HOSTILE, listeners=Source{}, listenerConditions=[MaterialCategory{category=FLUID}]}"
```

Plays the enderman hurt sound at the source location. The pitch will vary by 10% randomly. Players can adjust the volume of the sound to their preference by changing their Hostile sound settings. Only the player who caused the mechanic (`listeners=Source{}`) can hear the mechanic, and only if they are in water/lava.&#x20;

{% hint style="danger" %}
`shoot.ak47close` and `shoot.ak47far` are sounds that I made up for the example. The sounds are not included in the WeaponMechanics resource pack.&#x20;
{% endhint %}
{% endtab %}

{% tab title="Example 3" %}
```yaml
Mechanics:
  - "Sound{sound=ENTITY_ENDERMAN_HURT, pitch=0.5, listenerConditions=[MaterialCategory{category=FLUID}]} @Target{}"
  - "Sound{sound=ENTITY_ENDERMAN_HURT, pitch=2.0, listenerConditions=[MaterialCategory{category=FLUID, inverted=true}]} @Target{}"
```

This example plays different sounds, but each player can only ever hear one of them. Both sounds use the `ENTITY_ENDERMAN_HURT` sound and will come from the target location.

The player will hear the lowest pitch sound if they are in fluid, but they will hear the highest pitch sound if they are not in fluid.&#x20;
{% endtab %}

{% tab title="Example 4" %}
```yaml
Mechanics:
  - "Sound{sound=ITEM_FLINTANDSTEEL_USE, volume=1, pitch=2, delayBeforePlay=5, listeners=Source{}}"
  - "Sound{sound=BLOCK_IRON_TRAPDOOR_OPEN, volume=1, pitch=1.8, delayBeforePlay=5, listeners=Source{}}"
  - "Sound{sound=ITEM_ARMOR_EQUIP_IRON, volume=1, pitch=1.75, delayBeforePlay=5, listeners=Source{}}"
  - "Sound{sound=ITEM_ARMOR_EQUIP_IRON, volume=1, pitch=1.25, delayBeforePlay=5, listeners=Source{}}"
  - "Sound{sound=BLOCK_IRON_DOOR_OPEN, volume=1, pitch=2, delayBeforePlay=6, listeners=Source{}}"
  - "Sound{sound=ITEM_ARMOR_EQUIP_IRON, volume=1, pitch=1.45, delayBeforePlay=6, listeners=Source{}}"
  - "Sound{sound=BLOCK_IRON_TRAPDOOR_CLOSE, volume=1, pitch=1.5, delayBeforePlay=25, listeners=Source{}}"
  - "Sound{sound=ITEM_ARMOR_EQUIP_IRON, volume=1, pitch=1.5, delayBeforePlay=25, listeners=Source{}}"
  - "Sound{sound=ITEM_FLINTANDSTEEL_USE, volume=1, pitch=1, delayBeforePlay=26, listeners=Source{}}"
  - "Sound{sound=BLOCK_IRON_DOOR_CLOSE, volume=1, pitch=1.8, delayBeforePlay=27, listeners=Source{}}"
  - "Sound{sound=BLOCK_IRON_TRAPDOOR_CLOSE, volume=1, pitch=1.5, delayBeforePlay=27, listeners=Source{}}"
  - "Sound{sound=BLOCK_IRON_TRAPDOOR_CLOSE, volume=1, pitch=1.8, delayBeforePlay=39, listeners=Source{}}"
  - "Sound{sound=ITEM_ARMOR_EQUIP_IRON, volume=1, pitch=1.8, delayBeforePlay=39, listeners=Source{}}"
  - "Sound{sound=BLOCK_IRON_DOOR_CLOSE, volume=1, pitch=2, delayBeforePlay=40, listeners=Source{}}"
  - "Sound{sound=BLOCK_IRON_TRAPDOOR_CLOSE, volume=1, pitch=1.4, delayBeforePlay=40, listeners=Source{}}"
  - "Sound{sound=BLOCK_IRON_TRAPDOOR_CLOSE, volume=1, pitch=1.35, delayBeforePlay=40, listeners=Source{}}"
  - "Sound{sound=ITEM_FLINTANDSTEEL_USE, volume=1, pitch=1.5, delayBeforePlay=40, listeners=Source{}}"
```

Plays a weapon reload sound but uses cleverly adjusted pitches on vanilla sounds. Only the source player can hear the sound.&#x20;
{% endtab %}
{% endtabs %}

