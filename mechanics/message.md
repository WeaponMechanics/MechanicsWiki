# Message

Sends a message in chat.

| Argument  | Description         | Default Value                              |
| --------- | ------------------- | ------------------------------------------ |
| `message` | The message to send | <mark style="color:red;">\*</mark>Required |

We use[ MiniMessage](https://docs.advntr.dev/minimessage/format.html) to parse messages, a text format that allows colors, links, hoverables, and many other features. MiniMessage also provides an [editor](https://webui.advntr.dev/) for you to build your messages! Check out the default colors below:

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>MiniMessage Default Colors Chart</p></figcaption></figure>

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Message{message=<gradient:#5e4fa2:#f79459>Hello There} @World{} ?Range{max=50}"
```

This message has a gradient of 2 colors, and is sent to every player in the world within 50 blocks.&#x20;
{% endtab %}
{% endtabs %}





