# Particle

The particle mechanic spawns particles. Particles can be used for special effects, including muzzle flashes, water splashes, blood, block particles, hit markers, and more!

| Argument           | Description                                                                                                                                                                                                                   | Default Value                              |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| `particle`         | Which [Particle](http://127.0.0.1:5000/s/IIUkVnlH40vVBzLhWWQ8/references#particle "mention") type to spawn                                                                                                                    | <mark style="color:red;">\*</mark>Required |
| `color`            | The [Color](http://127.0.0.1:5000/s/IIUkVnlH40vVBzLhWWQ8/ "mention") of the particle (Only for `REDSTONE`, `SPELL_MOB` or `DUST_COLOR_TRANSITION`)                                                                            | None                                       |
| `fadeColor`        | The [Color](http://127.0.0.1:5000/s/IIUkVnlH40vVBzLhWWQ8/ "mention") for the particle to fade into (Only for `DUST_COLOR_TRANSITION`)                                                                                         | None                                       |
| `size`             | The scale of the particle (Only for `REDSTONE` or `DUST_COLOR_TRANSITION`). A number like 0.5 makes the particle half size.                                                                                                   | 1.0                                        |
| `count`            | Defines how many particles to spawn                                                                                                                                                                                           | 1                                          |
| `noise`            | Defines how randomly to spread out particles. This uses [Vector](http://127.0.0.1:5000/s/IIUkVnlH40vVBzLhWWQ8/vector "mention"). For example, `1 2 1` will spread the particles 1 block horizontally and 2 vertically.        | 0.0 0.0 0.0                                |
| `velocity`         | Defines how the particle moves. This uses [Vector](http://127.0.0.1:5000/s/IIUkVnlH40vVBzLhWWQ8/vector "mention").                                                                                                            | 0.0 0.0 0.0                                |
| `alwaysShow`       | Use `true` if you want players >40 blocks away to see the particle.                                                                                                                                                           | false                                      |
| `viewers`          | This is a [#targeter](../#targeter "mention") that defines who can see the firework. Please do not use the `@` symbol; remove it for this. [What is this option?](https://youtu.be/pFsVM4fQNHo)                               | World{}                                    |
| `viewerConditions` | This is a list of conditions that defines who can hear the sound. This is used to create per-player sound effects. Please do not use the `?` symbol; remove it for this. [What is this option?](https://youtu.be/pFsVM4fQNHo) | \[]                                        |

{% hint style="warning" %}
Not all particles support the `velocity` argument. Most support it, but if the particle does not support it you will see a warning in console.&#x20;
{% endhint %}

{% hint style="danger" %}
Do not use the `count` argument (Which defines how many particles to spawn) if you want to spawn 1 particle. MechanicsCore will automatically fill in the value. This is especially important if you use the `velocity` argument, which does not support `count`.&#x20;

To spawn multiple particles while using `velocity`, copy and paste your entire ParticleMechanic and change the velocity for each particle you want to spawn.&#x20;
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Particle{particle=FLAME}"
```

&#x20;Spawns 1 flame particle on the source entity.&#x20;
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Particle{particle=FLAME, shape=Sphere{points=100, radius=2}} @Source{eye=true}"
```

Spawns 1 flame particle on 100 evenly spaced points on a sphere with a radius of 2 around the source entity. Instead of spawning the sphere around the entity's feet, it will be around its head.&#x20;

![](<../.gitbook/assets/image (3).png>)
{% endtab %}

{% tab title="Example 3" %}
```yaml
Mechanics:
  - "Particle{particle=DUST_COLOR_TRANSITION, color=#FF0000, fadeColor=#00FF00, repeatAmount=10, repeatInterval=10} @Target{}"
```

Spawns 1 dust particle that changes color from red to green. The particle will spawn 10 times (1 time every half second, since 10 ticks = 0.5 seconds).&#x20;

Here is the wiki for [Color](http://127.0.0.1:5000/s/IIUkVnlH40vVBzLhWWQ8/ "mention")
{% endtab %}
{% endtabs %}



