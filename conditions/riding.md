# Riding

The riding condition checks if the entity is currently mounted onto another entity. For example, a player might be riding a horse or pig. A skeleton might be riding a spider.&#x20;

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Message{message=You are riding} ?Riding{}"
  - "Message{message=You are not riding} ?Riding{inverted=true}"
```
{% endtab %}
{% endtabs %}
