# Entity Type

The entity type condition checks which mob an entity is (a player? a zombie? a pig?)

| Argument | Description            | Default Value                              |
| -------- | ---------------------- | ------------------------------------------ |
| `entity` | Which entity to target | <mark style="color:red;">\*</mark>Required |

Use the [entities](https://app.gitbook.com/s/IIUkVnlH40vVBzLhWWQ8/references#entities "mention") reference for a full entity list.

{% tabs %}
{% tab title="Example 1" %}
<pre class="language-yaml"><code class="lang-yaml">Mechanics:
  - "Ignite{time=200} @World{} ?EntityType{entity=PIG}"
<strong>  - "Particle{particle=FLAME, count=15, spread=0.5 0.5 0.5} @World{} ?EntityType{entity=PIG}"
</strong></code></pre>

This lights all pigs in the world on fire for 10 seconds. It also spawns in some flame particles.
{% endtab %}
{% endtabs %}



