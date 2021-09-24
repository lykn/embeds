Not much of "coding" as per say. But, a basic embed structure for a Discord Bot, namely, [Noumenon](https://discord.com/oauth2/authorize?client_id=634866217764651009&permissions=2080894207&scope=bot+applications.commands), whose TagScript Engine powers many more bots like FriskyTool, and Kronos.

`\n`, Represents a new line, which denotes a "space"(Pretty basic)

If you would like to chance the color of this embed then all you need to do is edit the value in the `""` after the `:` for the `color` part of the embed(EG: `"color":"<value_here>"`)

[This](https://www.colorhexa.com) website would help you out a lot, figuring out the colors(Color used here is `Cyan(#00FFFF)`)

TagScript Documentation for the bot can be found [here](https://phen-cogs.readthedocs.io/en/latest/) -> Bot docs can be used to find default variables which store some pre-entered data(EG: `{author(name)}#{author(discriminator)}` on output would be `Lykn#0001`, in my case)

Default Variables from the bot's docs can be used anywhere in the code, including the footer(where text modifications like bolding, underlining, etc... don't work). When it comes to the embed footer, icon URL variables like `{author(avatar)}` or `{server(icon)}`, can be used and nothing else, because the stated ones only produce URL(normal copy paste URLs can also be used)

Make sure to add a `,` after every single `"` and look for braces which have not been closed

Reach out to me on Discord at `Lykn#0001` for anything

The following example shows you how to implement an embed into your tag or anywhere else. Basically meaning, it shows you how an embed words when you use it for a custom tag or a native action, but, when implementing. This will not work then you say `[p]embed json`, but, th

```
{embed({
      "title":"The Title Of the Embed goes Here",
      "color":65535,
      "description":"This embed is an example of a basic feature rich embed\n\nNew lines can be added by adding a `\n`\n`Code Block` are also supported\n`**Bold**`**is supported**\n`*Italics*` *are also supported*\n`__Underline__` __also works__\n\n[Hyperlinks](https://www.github.com/) also works!\n\nYou can also use emojis. Default ones like :one: or :two: would work normally. While custom ones, can be used but, by adding a `\\` before the emoji's first `:`(EG: `\\:emoji_name:`).\nThe emoji would transform to this format `<a:emoji_name:{a_bunch_of_numbers}>`",
 "footer": {
 "text":"Footer text appears here",
 "icon_url":"{author(avatar)}"
 }
})}
```
