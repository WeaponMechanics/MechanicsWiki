# Sprinting

The sprinting condition checks if the player is sprinting (running, or sprint swimming).

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Message{message=You are sprinting} ?Sprinting{}"
  - "Message{message=You are not sprinting} ?Sprinting{inverted=true}"
```
{% endtab %}
{% endtabs %}
