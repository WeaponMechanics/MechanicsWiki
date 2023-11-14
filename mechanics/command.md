# Command

The command mechanic causes either:

1. The console to run a command with OP
2. A player to run a command with their permissions

| Argument  | Description                                                                       | Default Value                              |
| --------- | --------------------------------------------------------------------------------- | ------------------------------------------ |
| `command` | The command to execute (you do not need a `/`)                                    | <mark style="color:red;">\*</mark>Required |
| `console` | Use `true` to run a console command. `false` will let the player run the command. | false                                      |

{% hint style="warning" %}
For a player/entity to run the command (`console=false`), they need _permission_ to run it.&#x20;
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Command{command=feed}"
```

Forces the source entity to run `/feed`, which fills the player's hunger.&#x20;

{% hint style="info" %}
The `/feed` command is added by [EssentialsX](https://essentialsx.net/)
{% endhint %}
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "Command{command=tp %source% 0 100 0, console=true}"
```

Forces the console to run `/tp CJCrafter 0 100 0` (assuming CJCrafter is the player who caused the mechanics). This is useful since CJCrafter probably doesn't have permission to teleport on your server, but this mechanic uses the console's permission.&#x20;
{% endtab %}
{% endtabs %}



