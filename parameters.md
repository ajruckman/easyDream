# easyDream command parameters

### `idea`
What you want the bot to dream about.

You can separate distinct ideas with `+`. For example, `prompt:new york times` is very different than `prompt:new york + times`:

| `new york times` | `new york + times` |
| --- | --- |
| ![new york times](https://cdn.discordapp.com/attachments/872973086654332989/881661629186580510/new_york_times.png) | ![new york + times](https://cdn.discordapp.com/attachments/872973086654332989/881661131255607296/new_york__times.png) |

Be aware that typos can dramatically change the output.

-----

### `preset`
Use a predefined set of parameters.

Some presets require features that only patrons have access to.

-----

### `size`
The size (width and height) in pixels of the output image. Limited to 196 for non-patrons.

High size values often cause the output to "fall apart" and lose cohesion. To create a cohesive but large image, you may want to start with a small `/imagine`. Then you can work your way up to a higher resolution using `/envision` like so:
1. `/imagine idea:planets exploding` -> `https://discordapp.com/.../planets_exploding.png` 🠞 ID `...1`
2. `/envision image:https://discordapp.com/...1/planets_exploding.png idea:planets exploding size:256` 🠞 ID `...2`
3. `/envision image:https://discordapp.com/...2/planets_exploding.png idea:planets exploding size:384` 🠞 ID `...3`
4. `/envision image:https://discordapp.com/...3/planets_exploding.png idea:planets exploding size:512`

-----

### `rounds`
How long to dream. Higher values produce more refined images, up to a plateau point depending on the optimizer and output size.

Here is how the prompt `/imagine idea:sci-fi cave` changes for increasing `rounds:`:

| 5 | 10 | 30 | 40 | 50 |
| --- | --- | --- | --- | --- |
| ![](https://cdn.discordapp.com/attachments/872973086654332989/881662948043530270/sci-fi_cave.png) | ![](https://cdn.discordapp.com/attachments/872973086654332989/881663223231827968/sci-fi_cave.png) | ![](https://cdn.discordapp.com/attachments/872973086654332989/881663025600397382/sci-fi_cave.png) | ![](https://cdn.discordapp.com/attachments/872973086654332989/881663193901064202/sci-fi_cave.png) | ![](https://cdn.discordapp.com/attachments/872973086654332989/881663070877913088/sci-fi_cave.png) |

-----

### `step-size`
How rapidly to think. Higher `step-size` values allow for quality results in fewer `rounds`. However, unreasonably high `step-size` values produce lower-quality images that are less like the prompt.

Changes to `step-size` result in totally different results, unlike changes to `rounds` which can be adjusted linearly.

-----

### `optimizer`
Which algorithm used to 'zero-in' on the output result. Different optimizers produce dramatically different results, and each optimizer has a different ideal `step-size` value for a given `rounds` value.

`/imagine` defaults to the `AdamP` optimizer. I have found it to be the best for from-scratch image generation.

`/envision` and `/meld` default to the `RMSprop` optimizer. I have found that this optimizer is great for morphing starter images quickly, but not so great for generating images from scratch.

See [this Algorithmia blog post](https://algorithmia.com/blog/introduction-to-optimizers) for better information about optimizers.

-----

### `initial-image` / `image` / `start`
An image to start from, as opposed to starting from a blank canvas. Must be a URL of an image uploaded to Discord.

For `/envision`, this parameter is named `image`. For `/meld`, this parameter is named `start`.

For safety reasons, easyDream can only see images that are hosted on Discord. Trying to give easyDream a link to an image *not* uploaded to Discord will not work. See [Use images in commands](/easyDream#use-images-in-commands) for how to upload images to Discord.

-----

### `idea-image` / `end`
An image version of an idea, as opposed to a text idea. Must be URLs of images uploaded to Discord.

The bot will identify features in this image and integrate those features into the result.

You can specify multiple idea image URLs with `+`. The bot will identify features in all specified idea images.

For safety reasons, easyDream can only see images that are hosted on Discord. Trying to give easyDream a link to an image *not* uploaded to Discord will not work. See [Use images in commands](/easyDream#use-images-in-commands) for how to upload images to Discord.

-----

### `augments`
Which filters to apply to image generated before each round. Separate multiple augments with `+`. The same augment can be used multiple times.

The default augments used to create every image are: `Af`+`Pe`+`Ji`+`Er`.

The following augments are available:
- `Ji`: ColorJitter
- `Sh`: RandomSharpness
- `Gn`: RandomGuassianNoise
- `Gb`: RandomGuassianBlur
- `Pe`: RandomPerspective
- `Ro`: Random Rotation
- `Af`: Random Affine
- `Et`: Random Elastic Transform
- `Ts`: Random Thin Plate Spline
- `Cr`: Random Crop
- `Er`: Random Erasing
- `Re`: Random Resized Crop
- `Gr`: Random Grayscale
- `Iv`: Random Invert
- `Pz`: Random Posterize
- `Sz`: Random Solarize
- `Fe`: Random Fisheye
- `Hf`: Random Horizontal Flip
- `None`: A dummy augment used to do nothing to the image

The order of augments matters significantly. For example, using `Gr`+`Ji` is very different than using `Ji`+`Gr`.
- `Gr`+`Ji` will convert the image to grayscale, then add random colors.
- `Ji`+`Gr` will add random colors, then turn the image to grayscale, effectively just adding noise to the image.
- `Ji`+`Gr`+`Ji` will add random colors, turn the image to grayscale, then add more random colors to the grayscale image.

For better results with specific prompts, you may wish to omit the `Ji` augment, as it can mess with the colors of the result.

Use the `None` augment if you don't want to use any augments (ideal for high-fidelity images).

See this [Kornia docs page](https://kornia.readthedocs.io/en/latest/augmentation.module.html) for ***visual examples*** of what these filters do.

-----

### `solid-fill`
A hex color code (like `#651fff`) to fill the empty starter canvas with. This option may have little to no effect on the output, depending on the `rounds`, `optimizer`, `step-size`, and `augments` values used; high rounds and step-sizes will completely obliterate the starter canvas in most cases, and some augments like ColorJitter or Desaturate alter colors so significantly that the starter color is irrelevant.

Additionally, this option draws a small square in the center of the image, filled with the inverse of the `solid-fill:` color. This is to help the bot recognize the significance of the `solid-fill:` value with contrast, and to help it "latch on" to the center of the image in order to grow outwards from there.
