Sending embeds is as easy as JSON or maybe easier.
When a Discord Bot responds in your server it's always those boring messages which it sends. Well, Discord has added a feature called `embeds` which spice things up in the message. Text markdowns and hyperlinking are just one of the many features of an embed.
This repo written and maintained by `Lykn#0009` shows the features of an embed, with full detailed explanation.
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
The above code signifies a weel sent and utilised embed
