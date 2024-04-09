# Title

The title mechanic can send a title and/or a subtitle that fades in and out on a player's screen. This covers most of the screen, so it can be used to send crucial messages.&#x20;

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

| Argument   | Description                                                                                | Default Value |
| ---------- | ------------------------------------------------------------------------------------------ | ------------- |
| `title`    | The message to display as the title                                                        | None          |
| `subtitle` | The message to display as the subtitle                                                     | None          |
| `fadeIn`   | The number of ticks for the title to fade in. This allows a smooth transition              | 10            |
| `stay`     | The number of ticks for the title to stay on screen after fading in, and before fading out | 70            |
| `time`     | The number of ticks for the title to fade out. This allows a smooth transition             | 20            |

We use[ MiniMessage](https://docs.advntr.dev/minimessage/format.html) to parse messages, a text format that allows colors, links, hoverables, and many other features. MiniMessage also provides an [editor](https://webui.advntr.dev/) for you to build your messages! Check out the default colors below:

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>MiniMessage Default Colors Chart</p></figcaption></figure>

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "Title{title=<gold>Big Message, subtitle=<gray>Little Message}"
```

This example demonstrates the difference in size between the title and the subtitle.&#x20;
{% endtab %}
{% endtabs %}



