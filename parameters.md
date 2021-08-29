# easyDream command parameters

### `prompt`
What you want the bot to dream about.

You can separate distinct ideas with `+`. For example, `prompt:new york times` is very different than `prompt:new york + times`:

| `new york times` | `new york + times` |
| --- | --- |
| ![new york times](https://cdn.discordapp.com/attachments/872973086654332989/881661629186580510/new_york_times.png) | ![new york + times](https://cdn.discordapp.com/attachments/872973086654332989/881661131255607296/new_york__times.png) |

Be aware that typos can dramatically change the output.

-----

### `preset`
Choose from a list of predefined parameter presets.

Some presets require features that only patrons have access to.

-----

### `rounds`
How long to dream. Higher values produce more refined images, up to a plateau point determined by the optimizer and output size.

Here is how the prompt `/imagine idea:sci-fi cave` changes for increasing `rounds:`:
| 5 | 10 | 30 | 40 | 50 |
| --- | --- | --- | --- | --- |
| ![](https://cdn.discordapp.com/attachments/872973086654332989/881662948043530270/sci-fi_cave.png) | ![](https://cdn.discordapp.com/attachments/872973086654332989/881663223231827968/sci-fi_cave.png) | ![](https://cdn.discordapp.com/attachments/872973086654332989/881663025600397382/sci-fi_cave.png) | ![](https://cdn.discordapp.com/attachments/872973086654332989/881663193901064202/sci-fi_cave.png) | ![](https://cdn.discordapp.com/attachments/872973086654332989/881663070877913088/sci-fi_cave.png) |

-----

### `step-size`
How rapidly to think. Higher `step-size` values allow for results in fewer `rounds`. However, unreasonbly high `step-size` values produce lower-quality images that are less like the prompt.
