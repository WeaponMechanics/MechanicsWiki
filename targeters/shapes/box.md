# Box

{% hint style="warning" %}
This requires WeaponMechanicsCosmetics to be installed
{% endhint %}

The `@Box{}` outlines an axis-aligned box. This can be used to show regions.&#x20;

| Argument                | Description                              | Default Value |
| ----------------------- | ---------------------------------------- | ------------- |
| `width`                 | The number of points to randomly select. | 1.0           |
| `height`                | The horizontal range of the cube.        | 1.0           |
| `distanceBetweenPoints` | The vertical range of the cube.          | 0.5           |

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Particle{particle=FLAME} @Box{width=2, height=3, eye=true}"
```

Spawns a 2x3 cube outline of flame particles.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Example 1 in action</p></figcaption></figure>
{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}
