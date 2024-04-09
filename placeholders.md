---
description: List of placeholders available in mechanics
---

# Placeholders

Sometimes, you may want to use the player's name when sending messages. Or you may want to send a message to the target warning them that a missile has locked onto them, and you use their name to get their attention. You can use the following placeholders in your messages and commands:

## Source Placeholders

| Placeholder     | Description                                                                                    |
| --------------- | ---------------------------------------------------------------------------------------------- |
| `<source_name>` | The name of the source entity. For Players, this will be their in-game name, like `CJCrafter`. |
| `<source_x>`    | The x coordinate of the source entity.                                                         |
| `<source_y>`    | The y coordinate of the source entity.                                                         |
| `<source_z>`    | The z coordinate of the source entity.                                                         |

## Target Placeholders

{% hint style="warning" %}
Not every mechanic has a target. For example, WeaponMechanics `Shoot.Mechanics` does not have any `@Target{}`, just a `@Source{}`.&#x20;
{% endhint %}

| Placeholder     | Description                                                                                  |
| --------------- | -------------------------------------------------------------------------------------------- |
| `<target_name>` | The name of the target entity. For Players, this will be their in-game name, like `DeeCaaD`. |
| `<target_x>`    | The x coordinate of the source entity.                                                       |
| `<target_y>`    | The y coordinate of the source entity.                                                       |
| `<target_z>`    | The z coordinate of the source entity.                                                       |

## Other Plugin Placeholders

Some plugins may add placeholders for you to use.

* [Placeholders](https://app.gitbook.com/s/9hOjsLnIiB5Xm8MOXgWU/placeholders "mention") from WeaponMechanicsPlus
