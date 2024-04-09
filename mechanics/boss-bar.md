# Boss Bar

The boss bar is the text at the top of the screen. It is used in vanilla Minecraft when you fight the Ender Dragon and the Wither.

{% hint style="warning" %}
Using multiple boss bars simultaneously will cause them to stack vertically on the screen.
{% endhint %}

| Argument   | Description                                                                                                      | Default Value                              |
| ---------- | ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| `title`    | The message to display above the boss bar                                                                        | <mark style="color:red;">\*</mark>Required |
| `color`    | The color of the bar itself. Choose from: `BLUE`, `GREEN`, `PURPLE`, `RED`, `WHITE`, or `YELLOW`                 | RED                                        |
| `style`    | The visual pattern of the bar. Choose from: `NOTCHED_6` `NOTCHED_10`, `NOTCHED_12`, `NOTCHED_20`, or `PROGRESS`  | PROGRESS                                   |
| `progress` | The percentage to fill up the bar                                                                                | 100%                                       |
| `time`     | The number of ticks for the bar to stay on screen.                                                               | 100                                        |

We use[ MiniMessage](https://docs.advntr.dev/minimessage/format.html) to parse messages, a text format that allows colors, links, hoverables, and many other features. MiniMessage also provides an [editor](https://webui.advntr.dev/) for you to build your messages! Check out the default colors below:

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>MiniMessage Default Colors Chart</p></figcaption></figure>

{% tabs %}
{% tab title="Example 1" %}
```yaml
Mechanics:
  - "BossBar{title=<gold>Every good boy deserves <bold>fudge</bold>!}"
```

Sends a boss bar to the source player with the message:

> <mark style="color:orange;">Every good boy deserves</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**fudge**</mark><mark style="color:orange;">!</mark>
{% endtab %}

{% tab title="Example 2" %}
```yaml
Mechanics:
  - "BossBar{title=50% off sale} @ServerPlayers{}"
```

Announces a 50% discount to all players connected to the server.&#x20;
{% endtab %}
{% endtabs %}



