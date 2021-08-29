# easyDream

![Examples](https://cdn.discordapp.com/attachments/881625677349142528/881634798580432956/monage1-comp.png)


### [Commands](#commands)

- `/imagine (description)` - create an image from a description (the "prompt"). For example: `/imagine idea:ethereal orange waterfall`
- `/envision image:(image link) idea:(description)` - morph an image to make it look like the description.
- `/meld start:(image link #1) end:(image link #2)` - meld some parts of the image in `link #2` into `#link 1`.

&nbsp;

### [Use images in commands](#use-images)

For safety reasons, easyDream can only see images that are hosted on Discord. Trying to give easyDream a link to an image *not* uploaded to Discord will not work.

This is an example of a link to an image hosted on Discord: `https://cdn.discordapp.com/attachments/881625677349142528/881626536762015775/image0.png`

To use your own images with easyDream, you must first upload them to Discord. You can do this a few ways:
- Saving the image as a file, then dragging and dropping it into the Discord window.
- Saving the image as a file, then clicking the "+" icon to the left of the box where you type in Discord messages, then uploading the image.
- Right clicking an image in your web browser, then clicking "Copy image", then pasting (Ctrl+V or Cmd+V) in the Discord window.

Once you have your image on Discord, you can get its link by right clicking on the image and clicking "Copy link":

![Where to click to Copy Link](https://cdn.discordapp.com/attachments/881625677349142528/881628628641792030/unknown.png)

Or on mobile, tap the image, then click the Share button, and copy the link to your clipboard.

&nbsp;

### [Slash Commands 101](#slash-commands-101)

easyDream uses **slash commands** rather than text commands. Slash commands make it easy to see the syntax for the command you want to run, and once you get the hang of them, they are much easier to use.

To use an easyDream command, start by typing `/` (forward slash), and then the name of the [easyDream command](#commands) you want to use. 

Each command has 1 or 2 *required* parameters. You will be prompted to enter these first. After you type a value for one parameter, press tab to set another one.

![Required parameter for imagine](https://cdn.discordapp.com/attachments/881625677349142528/881638189369020456/unknown.png)

Most parameters are optional, and have reasonable defaults.

&nbsp;

### [Parameter explanations](#parameter-explanations)

&nbsp;

### [Examples](#examples)

Examples for `/imagine idea:`...

| neon smog | sapphire radiance | lava cliff | explosion nebula | melting spaceship | spiderweb abyss darkness |
| --- | --- | --- | --- | --- | --- |
| ![neon smog](https://cdn.discordapp.com/attachments/881625677349142528/881643419032756254/neon_smog.png) | ![sapphire radiance](https://cdn.discordapp.com/attachments/872973086654332989/881629324455837766/sapphire_radiance.png) | ![lava cliff](https://cdn.discordapp.com/attachments/872973086654332989/881644424663294052/lava_cliff.png) | ![explosion nebula](https://cdn.discordapp.com/attachments/872973086654332989/881646300104380476/explosion_nebula.png) | ![melting spaceship](https://cdn.discordapp.com/attachments/872973086654332989/881646845275811881/melting_spaceship.png) | ![spiderweb abyss darkness](https://cdn.discordapp.com/attachments/872973086654332989/881339740752842812/spiderweb_abyss_darkness.png) |

Examples for `/envision image:https://cdn.discordapp.com/attachments/881625677349142528/881653311785287710/kingfisher.png idea:`...

| `image:` input | steampunk | high calibre rifle rounds | scifi robot | long black veil | star wars |
| --- | --- | --- | --- | --- | --- |
| ![Start image (the `image:` parameter)](https://cdn.discordapp.com/attachments/881625677349142528/881653311785287710/kingfisher.png) | ![steampunk](https://cdn.discordapp.com/attachments/872973086654332989/881652650645532752/steampunk.png) | ![high calibre rifle rounds](https://cdn.discordapp.com/attachments/872973086654332989/881648879873982484/high_calibre_rifle_rounds.png) | ![scifi robot](https://cdn.discordapp.com/attachments/872973086654332989/881649097566740480/scifi_robot.png) | ![long black veil](https://cdn.discordapp.com/attachments/872973086654332989/881650310894981151/long_black_veil.png) | ![star wars](https://cdn.discordapp.com/attachments/872973086654332989/881652950408261702/star_wars.png) |

&nbsp;

See more examples with parameters at [Examples](examples).

&nbsp;

### [Keywords to try](#keywords)

These keywords can be used in the `idea` parameter for `/imagine` or `/envision` to make some really cool images:
- iridescent, prismatic, ethereal, neon
- chasm, abyss, rift
- nebula, galaxy, stardust
- underwater, hall
- darkness, vapor, mist
- lava, honeycomb, bubble
- amethyst, azurite, malachite, obsidian, gold, ruby, sapphire
- yeti, alduin, peacock
