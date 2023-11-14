# Sneaking

The sneaking condition checks if the player is holding the shift key to sneak.

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Message{message=You are sneaking} ?Sneaking{}"
  - "Message{message=You are not sneaking} ?Sneaking{inverted=true}"
```
{% endtab %}
{% endtabs %}
