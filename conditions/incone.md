# InCone

The `InCone` condition lets you check if entities are in a cone.

| `angle`     | The angle, in degrees, of the cone.                                                                                               | 0                  |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------- | ------------------ |
| `direction` | The direction vector of the cone. Uses the [Vector](https://app.gitbook.com/s/IIUkVnlH40vVBzLhWWQ8/vector "mention") serializer.  | `~0 0 1` (forward) |

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>A cone diagram</p></figcaption></figure>

In the diagram above, the `angle` argument is the same thing as $$\theta$$.

{% hint style="warning" %}
The `InCone` argument defines an _infinite cone_. This means, that when you want to want to  specify the distance (or the $$h$$ argument in the diagram above), you should use the [range.md](range.md "mention") condition as well.
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
This example creates an `RPG_7` [back blast](https://youtu.be/OZaNtK1l8cI?t=308) effect in `Shoot.Mechanics`:

```yaml
Mechanics:
  - "CustomSound{sound=shoot.rpg7.loud, volume=6, noise=0.1}"
  - "Damage{damage=10.0} @World{} ?Range{max=4} ?InCone{direction=~0 0 -1, angle=28}"
```
{% endtab %}
{% endtabs %}
