# Home

{% embed url="https://youtu.be/q8Oh2qsiCH0" %}
Mechanics Tutorial
{% endembed %}

Mechanics is a _"simple"_ scripting language that lets you create custom actions (like sending a message or spawning a firework). Across our wikis, you often see a config key and then `<Mechanics>`, like this:

```yaml
Weapon_Get_Mechanics: <Mechanics>
```

Whenever you see those `<Mechanics>`, that means you use all the features from this wiki!

## Getting Started

Each line consists of 3 components:

<table><thead><tr><th width="159">Component</th><th width="206">Description</th><th>Example</th><th data-type="checkbox">Optional</th></tr></thead><tbody><tr><td><a data-mention href="./#mechanic">#mechanic</a></td><td>The action</td><td><code>Sound{sound=ENTITY_GENERIC_EXPLODE}</code></td><td>false</td></tr><tr><td><a data-mention href="./#targeter">#targeter</a></td><td>Who the action affects</td><td><code>@Source{}</code></td><td>true</td></tr><tr><td><a data-mention href="./#conditions">#conditions</a></td><td>Filter out who to affect</td><td><code>?Biome{biome=PLAINS}</code></td><td>true</td></tr></tbody></table>

## Mechanic

The first and most crucial component is the Mechanic, which defines the action. Here is an example that sends a message to the player who caused the mechanic:

```yaml
  - "Message{message=This is a Mechanic}"
```

Each mechanic has arguments. For the mechanic above, `message` is an argument. Every mechanic  can use the following arguments:

| Argument         | Description                                      | Default Value                                 |
| ---------------- | ------------------------------------------------ | --------------------------------------------- |
| `repeatInterval` | The number of ticks between repeating mechanics  | $$1$$                                         |
| `repeatAmount`   | How many times to repeat the mechanic            | $$1$$                                         |
| `delay`          | The number of ticks before the mechanic executes | $$0$$ (instant)                               |
| `chance`         | The random chance the mechanic executes          | <p><span class="math">100\%</span></p><p></p> |

```yaml
  - "Message{message=This is a Mechanic, repeatInterval=20, repeatAmount=5, delay=200, chance=50%}"
```

This mechanic has a $$50\%$$ chance of executing. If it does execute, after $$10$$ seconds ($$200\text{ ticks}=1\text{ second}$$), 5 messages will be sent with $$1$$ second between each message.&#x20;

## Targeter

Targeters choose the "_who_" and the "_where_" the mechanic happens. For example, for a message, you should target a player. For some mechanics, like `Message{}`, you need to target an entity instead of a player.&#x20;

Targeters always start with an `@` character. A Targeter is not required, since it defaults to `@Source{}`. This means both of these are equivalent:

```yaml
  - "Sound{sound=ENTITY_GENERIC_EXPLODE}"
  - "Sound{sound=ENTITY_GENERIC_EXPLODE} @Source{}"
```

Some targets use arguments. Every Targeter can use the following arguments:

<table><thead><tr><th width="129.33333333333331">Argument</th><th width="450">Description</th><th>Default Value</th></tr></thead><tbody><tr><td><code>offset</code></td><td>Offset the XYZ coordinates. You can use relative directions using <code>~</code>. See <a data-mention href="http://127.0.0.1:5000/s/IIUkVnlH40vVBzLhWWQ8/vector">Vector</a> for more information.</td><td><span class="math">0\ 0\ 0 </span></td></tr><tr><td><code>eye</code></td><td>Target the entity's eye location instead of the location of its feet. </td><td>false</td></tr></tbody></table>

```yaml
  - "Sound{sound=ENTITY_GENERIC_EXPLODE} @Source{eye=true, offset=~0 0 1}"
```

This mechanic will play the explosion sound 1 block in front of the eyes of the entity that caused the mechanics.

## Conditions

Conditions let you filter out specific targets. You can use as many Conditions as you want. By default, no conditions are used. Conditions always start with a `?` character.&#x20;

Every Condition can use the `inverted=true/false` argument. When `true` the condition will be _inverted_, meaning the opposite must be true. For example:

```yaml
"?Biome{biome=PLAINS}"  # only works in the plains biome
"?Biome{biome=PLAINS, inverted=true}"  # works in every biome EXCEPT plains
```

