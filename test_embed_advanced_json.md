The following JSON is an example of using rich embeds using the one of the rich embed creator cogs. If you want to customize the color of the embed, you will need to go to the following website: [ColorHexa](https://www.colorhexa.com) - and convert the HEX/RGB value of the color into decimal and use that for the color value for your embed.

```json 
{
   "title":"Test JSON Embed",
   "description":"This embed is an example of a basic feature rich embed\n\nNew lines can be added by adding a `\n`\n`Code Block` are also supported\n`**Bold**`**is supported**\n`*Italics*` *are also supported*\n`__Underline__` __also works__\n\n[Hyperlinks](https://www.github.com/) also works!\n\nYou can also use emojis. Default ones like :one: or :two: would work normally. While custom ones like :thonking:, can be used but, by adding a `\\` before the emoji's first `:`(EG: `\\:emoji_name:`).\nThe emoji would transform to this format `<a:emoji_name:{a_bunch_of_numbers}>`",
   "url":"https://www.website.com/",
   "color":65535,
   "fields":[
      {
         "name":"Field A",
         "value":"This field is __not__ inline"
      },
      {
         "name":"Field B",
         "value":"This field is also not in a line"
      },
      {
         "name":"Field C",
         "value":"But, this field __is inline__",
         "inline":"true"
      },
      {
         "name":"Field D",
         "value":"And, so is this one!",
         "inline":"true"
      }
   ],
   "author":{
      "name":"Lykn",
      "url":"https://www.github.com/lykn/",
      "icon_url":"https://images-ext-1.discordapp.net/external/E7AVN-NDLGG7RDUthVklziwBDjlMeTZdN9TX-SJhJ7g/%3Fsize%3D1024/https/cdn.discordapp.com/avatars/779347811099475978/a_b34da4dffa6c02a7d3f3e98698caa1eb.gif?width=364&height=364"
   },
   "footer":{
      "text":"This is the footer. Footer text appears here. Custom emojis, and text modifications __won't__ work here",
      "icon_url":"https://www.link.to/some/image.png"
   },
   "image":{
      "url":"https://www.link.to/some/image.png"
   },
   "thumbnail":{
      "url":"https://www.link.to/some/image.png"
   }
}
```
