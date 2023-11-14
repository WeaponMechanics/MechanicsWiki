# 🌊 GeyserMC

GeyserMC allows both Bedrock players and Java players to connect to the same server.&#x20;

***

## Geyser Condition

The `Geyser{}` condition checks to see if an entity is a Bedrock player.&#x20;

```yaml
Mechanics:
  - "Message{message=You are a bedrock player} ?Geyser{}"
  - "Message{message=You are not a bedrock player} ?Geyser{inverted=true}"
```
