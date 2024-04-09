# Action Bar

The action bar is the text present above the item. It is used in vanilla Minecraft when you try to sleep with monsters nearby.&#x20;

{% hint style="warning" %}
Many plugins use the action bar to display information or to add more health bars. Using this Mechanic may temporarily override those.&#x20;
{% endhint %}

| Argument  | Description                                      | Default Value                              |
| --------- | ------------------------------------------------ | ------------------------------------------ |
| `message` | The message to display in the action bar.        | <mark style="color:red;">\*</mark>Required |
| `time`    | The time, in ticks, for the message to be shown. | 40                                         |

We use[ MiniMessage](https://docs.advntr.dev/minimessage/format.html) to parse messages, a text format that allows colors, links, hoverables, and many other features. MiniMessage also provides an [editor](https://webui.advntr.dev/) for you to build your messages! Check out the default colors below:

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>MiniMessage Default Colors Chart</p></figcaption></figure>

{% hint style="info" %}
`time` should always be a number >40, since action bars MUST be present for at least 40 ticks. Remember that 20 ticks = 1 second.&#x20;
{% endhint %}

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "ActionBar{message=<yellow>Hello World}"
```

Shows "Hello World" to the source player for 40 ticks (2 seconds).
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "ActionBar{message=You will see this for 3. seconds, time=70}"
```

Sends an action bar message to the source player for 70 ticks, or 3.5 seconds.&#x20;
{% endtab %}
{% endtabs %}



