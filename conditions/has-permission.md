# Has Permission

The has permission condition checks whether the target entity has a permission.

| Argument     | Description                   | Default Value                              |
| ------------ | ----------------------------- | ------------------------------------------ |
| `permission` | Which permission to check for | <mark style="color:red;">\*</mark>Required |

Not sure which permission to use? Use the [LuckPerms Web Editor](https://luckperms.net/editor) to see all permissions on your server.&#x20;

{% hint style="info" %}
All entities have access to permissions (like zombies)! If you only want players, add:

```
?EntityType{entity=PLAYER}
```
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Message{message=Damn you are op} @ServerPlayers{} ?HasPermission{permission=essentials.op}"
```

Sends a message to all players on the server who have the `essentials.op` permission.
{% endtab %}
{% endtabs %}



