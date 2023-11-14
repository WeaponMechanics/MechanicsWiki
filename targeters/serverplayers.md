---
description: Selects all players connected to the server
---

# ServerPlayers

The `@ServerPlayers{}` targeter selects all players currently connected to your Minecraft server.

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Title{title=<rainbow>10% off sale} @ServerPlayers{}"
```

This mechanic sends a rainbow title to all players connected to the server.&#x20;
{% endtab %}
{% endtabs %}
