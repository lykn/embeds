Sending embeds in Python is as easy as JavaScript or maybe easier.

When a Discord Bot responds in your server it's always those boring messages which it sends. Well, Discord has added a feature called `embeds` which spices things up in the message. Text markdowns and hyperlinking are just one of the numerous features of an embed.

This repo written and maintained by `Lykn#0009` shows the features of an embed, with a full detailed explanation for everything.

Main Links:
 - [ColorHexa](https://www.colorhexa.com/) will help you pick colors for your embed(s)
 - Click [here](https://discordpy.readthedocs.io/en/latest/api.html#discord.Embed) for Discord's Official discord.py Docs on `embeds`
 - Click [me](https://cog-creators.github.io/discord-embed-sandbox/) for a discord.py Embed Builder(gives you a preview of your embed and shows you the Python code to it - Interactive Website)
 - Click [this](https://www.discordpy.readthedocs.io/en/latest/api.html) for Discord's Official discord.py Docs(the whole thing)
 - Click [this link](https://github.com/Rapptz/discord.py/) for a read-only discord.py repository which has alomst everything needed for a discord.py programmer
 - Click [on this](https://www.discord.com/invite/discord.api) for Discord's API Server
 - Click [over here](https://www.discord.com/invite/dpy) for Discord Official Verified Discord Server(discord.py help also available here
 
**First, I'm going to be showing the code to a fully utilised embeds, using everything that the docs offer, I'm going to be breaking up everything and showing you each and every feature**
```py 
import discord
from discord.ext import commands 

client = commands.Bot(command_prefix = "!", intents = discord.Intents.all(), status = discord.Status.dnd, activity = discord.Game(name = "with Embeds")) # Declaration of the `client`. `bot` can also be used here, and, if you use `bot` then just replace `client` with `bot` everywhere
# This doesn't mean a lot, I mean it does, but, in this file this doesn't have any meaning it's just a basic skeletal structure of a discord.py bot

@client.event
async def on_ready()
 print('The bot is now up and running')
 print(f'Logged in as {client.user.name}({client.user.id})')
 print('-----------------------------------------------------')
# This is just a very basic `on_ready` print message 

@client.command() # Pay attention from here becuase we do the main embed command comes in
async def embed(ctx): # Declaration of the command and use `ctx` as the context of the message. You can use `message` also, and, if you do so then just replace `ctx` with `message` in this code
 em = discord.Embed(title = "**Title Goes Here**", color = discord.Color.blue(), description = "The embed description goes here and all sorts of text modification and code blocks work here!", url = "https://www.discords.com/bio/lykn/") # Here, I have said `color = discord.Color.blue()` but hex, and hexadecimals can be used, but, make sure to add it inside two(2) `"`(color = "<hex_or_hexadecimals_here>")
 # `em` is like a variable, you, can all it whatever you want. But, `discord.Embed` is constant, because, it's from the docs and can't be changed. Basically everything after the `=` is constant and from the docs click the second link to read it 
 em.set_author(name = 'Lykn#0009', icon_url = 'https://www.link.to/some/image/', url = 'https://www.github/lykn/') # `set`'s an author, because, this is something that's pre existing and doesn't need to be `add`ed like field which will be shown later on
 em.set_footer(text = f"This test embed was sent by {ctx.author.display_name}", icon_url = "{ctx.author.avatar_url}") # Same thing as the `author`(`header`) but `name` is replaced with `text` and `url` isn't an option here
 em.add_field(name = "**Field 1**", value = "This is where a field's value is.\nThis field is __not__ inline", inline = False) # Since this is a field it is `add`ed and not `set` 
 em.add_field(name = "**Field 2**", value = "This is where the seconds field's value is.\nAgain __not__ inline", inline = False) # `name` is like the header of the field, `value` is the information it contains, and, lastly `inline` is a bool and the only two options you can use are `True` or `False`(the third and fourth field are inline, for an example)
 em.add_field(name = "**Field 3**", value = "This is the third field and unlike the first and seconds fields this one __is__ inline", inline = True)
 em.add_field(name = "**Field 4**", value = "This is the fourth field and it __is__ inline with teh third field", inline = True)
 
 await ctx.send(embed = em) # Here `embed` is constant, but, `em` is not, it will be whatever you use in the first part(`em = discord.Embed`) so make sure to check that
```
The above code signifies a well utilised embed.
Now lets start breaking down the components.

**1. A Basic Embed**

Not going to be adding the `on_ready` and commands stuff, but, cutting the chase and going right into the embeds part 

What a basic embed has:
 - `title` 
 - `color` 
 - `url`

Basic Code:
```py
em = discord.Embed(
title = "Embed Title",
color = "#00FFFF" # Makes the embed color to cyan and not the default black
)
```

Now the url. `url` is just a hyper link for the title(hyperlinks the entire string of text)
```py
em = discord.Embed(
title = "Embed Title",
color = "#00FFFF",
url = "https://www.github/lykn/" # Hyperlinks the text "Embed Title" with my(Lykn's) github profile
)
```
When a user click the title Discord will ask the user with a pop saying, "Are you sure you would like to go to **https://www.github/lykn/**"

**2. Tweking the `color` part**

Supposing you don't know hex codes and don't want to get your hands dirty with it too. Discord has a fix for it.
Insted of going `color = "#00FFFF"`, to get a blue*ish* cyan Discord has a preset pallete of colors and for our example shows before it is `discord.Color.blue()`
Putting this to the test with a code
```py
em = discord.Embed(
title = "Embed Title",
color = discord.Color.blue(), # You don't add the `""` when you use `discord.Color` but you need to add a `()` right after the color. Also the `,` is constant for everything because that's what differentiates between the different categories
url = "https://www.github/lykn/" 
)
```
Some points to not when you use `discord.Color`
 - Don't add the two `""` when using this 
 - Make sure to add the `()` at the end 
 - Format: `discord.Color.<color_name>()`
 -
 
**3. Adding an `author`**

What is an author?
> The text that appears on the top of the embed is know as the `author` area. Basically its just a "fancy" way to call a `header`

Basic Code:
```py
em = discord.Embed(
title = "Embed Title",
color = discord.Color.blue(), # You don't add the `""` when you use `discord.Color` but you need to add a `()` right after the color. Also the `,` is constant for everything because that's what differentiates between the different categories
url = "https://www.github/lykn/" 
)
em.set_author(name = "Lykn#0009", icon_url = "https://www.link.to/some/image.png", url = "https://github.com/lykn/") # Here the `author` has to be `set` and not `add`ed because it's a default field(option - if you don't want to get confused)
```
Things to note:
 - Text markdowns don't work here 
 - Code blocking won't work here
 - If you would wise to copy past text from websites like [LingoJam](https://lingojam.com/TextFonts)

If you would like to use the user's `icon_url` and `name` as the header then follow the below code(as a command) using `ctx`(`message` can also be used)
Code:
```py
@client.command() # `client` has been used, but, this can also be replaced with `bot` or anything you use in the `______ = commands.Bot(command_prefix = "")` part
async def embed(ctx):
 em = discord.Embed(
title = "Embed Title",
color = discord.Color.blue(), # You don't add the `""` when you use `discord.Color` but you need to add a `()` right after the color. Also the `,` is constant for everything because that's what differentiates between the different categories
url = "https://www.github/lykn/" 
)
 em.set_author(name = "Lykn#0009", icon_url = "https://www.link.to/some/image.png", url = "https://github.com/lykn/") # Here the `author` has to be `set` and not `add`ed because it's a default field(option - if you don't want to get confused)
```


**4. Adding a `footer`**
> A footer as the name suggests is what appears on the bottom of the embed
Basic Attributes:
 - `text` - String of text what appears
 - `icon_url` - Image which appears beside(left) the text 

Basic Code:
```py
em = discord.Embed(
title = "Embed Title",
color = discord.Color.blue(), # You don't add the `""` when you use `discord.Color` but you need to add a `()` right after the color. Also the `,` is constant for everything because that's what differentiates between the different categories
url = "https://www.github/lykn/" 
)
em.set_author(name = "Lykn#0009", icon_url = "https://www.link.to/some/image.png", url = "https://github.com/lykn/") # Here the `author` has to be `set` and not `add`ed because it's a default field(option - if you don't want to get confused)
em.set_footer(text = "Embed footer comes here!", icon_url = "https://www.link.to/some/image.png") # I'm continuing with the same code after every section by just adding the content of that section to the main code
```
