---
description: Mechanics and Conditions added for MythicMobs
---

# 👽 MythicMobs

MythicMobs is a custom mob creation plugin with an advanced skills system. Their skill system allow custom mythic mob entities to cast special abilities.&#x20;

We add the following mechanics for MythicMobs users:

1. [#mythic-skill-mechanic](mythicmobs.md#mythic-skill-mechanic "mention")
2. [#mythic-mobs-entity-condition](mythicmobs.md#mythic-mobs-entity-condition "mention")
3. [#mythic-mobs-faction-condition](mythicmobs.md#mythic-mobs-faction-condition "mention")

{% hint style="success" %}
MythicMobs inspired our Mechanics system, which is why we use similar formats!
{% endhint %}

***

## Mythic Skill Mechanic

The `MythicSkill` mechanic allows you to execute a [Skill](https://git.mythiccraft.io/mythiccraft/MythicMobs/-/wikis/skills/mechanics/skill). This lets you use MythicMob's skill system. You can summon mobs, shoot volleys, and many other things. Check out their wiki for a complete list.&#x20;

MythicMobs wiki: [https://git.mythiccraft.io/mythiccraft/MythicMobs](https://git.mythiccraft.io/mythiccraft/MythicMobs)

| Argument | Description                                                     | Default Value                              |
| -------- | --------------------------------------------------------------- | ------------------------------------------ |
| `skill`  | Which skill to execute                                          | <mark style="color:red;">\*</mark>Required |
| `power`  | Determines the power variable, if you are a Mythic Premium user | 1.0                                        |

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "MythicSkill{skill=SpawnSkeletons}"
```

Runs the `SpawnSkeletons` skill, with the source entity being the cause and trigger.
{% endtab %}
{% endtabs %}

***

## Mythic Mobs Entity Condition

The `MythicMobsEntity` condition checks to see if a targeted entity is a specific type of mythic mob. This lets you target specific mythic mobs.&#x20;

| Argument | Description               | Default Value                              |
| -------- | ------------------------- | ------------------------------------------ |
| `entity` | Which mythic mob to check | <mark style="color:red;">\*</mark>Required |

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Potion{potion=POISON} @World{} ?MythicMobsEntity{entity=Skeleton_King}"
```

This example poisons all skeleton king mythic mobs in the current world.&#x20;
{% endtab %}
{% endtabs %}

***

## Mythic Mobs Faction Condition

The `MythicMobsFaction` condition checks to see if a targeted entity is a part of a faction from MythicMobs. This can be used to make `undead` creates immune to a mechanic (for example).

| Argument  | Description                                  | Default Value                        |
| --------- | -------------------------------------------- | ------------------------------------ |
| `faction` | Which faction should the entity be a part of | <mark style="color:red;">None</mark> |

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Potion{potion=LEVITATION} @World{} ?MythicMobsFaction{faction=undead}"
```

This example makes all undead mobs in the world levitate.
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Potion{potion=LEVITATION} @World{} ?MythicMobsFaction{}"
```

This example makes all mobs who **ARE** a MythicMob but **ARE NOT** a part of a faction levitate.
{% endtab %}
{% endtabs %}



