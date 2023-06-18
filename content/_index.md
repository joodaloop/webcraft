---
title: "Guide"
description: "Guide • Streams"
---

This site contains details that go beyond basic usage of the Streams bot. If you've ever wanted to learn about all the bot [commands](/commands), use the fancier [markdown](#markdown) syntax, export your data, or use the simple Streams [API](/api), this is the place for it. 

## Features 

Non-exhaustive list of features offered by streams.place. 

| Feature | Details |
|-|-|
| **RSS feed** | Available at *your-url/rss* |
| **API** | GET/POST endpoints, check the [API](/api) page. |
| **Protected drops** | The [/protect](/commands#protect) command hides Drops to your private Stream (*your-url/keyphrase*)|
| **Theme editor** | Use the editor at *your-url/editor/your-keyphrase* to create your own themes |
| **Search** | By both date (syntax: year-month-day), and keyword |
| **Export/migration** | The markdown for all your posts is available at *your-url/export/keyphrase* |
| **Storage for images, files and audio** | As long as they are smaller than 2MB | 
| **LaTeX** | Check out the syntax in the [Markdown](#markdown) section |

**Note:** There are [/export](/commands#export), [/rss](/commands#rss), and [/editor](/commands#editor) that will provide you with links to all those pages whnever you want them.


## Privacy

In the database, your Stream is associated with your Telegram ID, which is a number that provides me with no private information. Your name, phone number and other profile data remains a secret. 

When you first create your Stream, your Telegram username is used as your username and as the Stream's title. You can easily change this, using the /newusername and /title commands. 

The transferring of messages to my bot is handled by Telegram, with whatever security protocols they have in place for their app as a whole. I can confirm that these message payloads do not contain any private information either. 

If you'd like to erase all trace of your account, [let me know](mailto:judah@joodaloop.com) and I'll get my best agents on the job.


## Markdown

The original markdown spec doesn't support certain elements (highlighting and LaTeX) that I wanted Streams to have. So I've had to extend the syntax using code blocks with special inital characters.

| Element | Markup |
|-|-|
| [a cool link]() | \[a cool link\]\(https://yourcoolurl.com\) |
| **bold text** | \*\*bold text\*\* |
| _italic_ | \_\_italic\_\_ |
| <mark>highlight</mark> | \`::highlight\` or \`==highlight\` |
| <img src="/media/katex.png" class=katex-image> | \`$ latex x_{2}\` or \`\`\`$ latex x_{2}\`\`\` |
| `inline code` | \`inline code\` |
| <pre class=inline> let x = "code block" </pre> | \`\`\`let x = "code block"\`\`\` |
| ~~strikethrough~~ | \~\~strikethrough\~\~ |
| <div class=quote> To be somebody or to do something...To be or to do? Which way will you go? </div> | > To be somebody or to do something...To be or to do? Which way will you go? |


## Theme Gallery

Themes are the simplest level of customization, each is different combination of fonts, highlight colors, and backgrounds. You can change between themes using the [/theme](/commands#theme) command.

### Classic
Dignified serif, plain old black & white.
![Screenshot of the Classic theme](/media/classic.jpg)

### Notebook
system-ui font, lightly-dotted background, yellow highlighting.

![Screenshot of the Notebook theme](/media/notebook.jpg)

### Dark
Avenir, easy on the eyes.
![Screenshot of the Dark theme](/media/dark.jpg)

### Royal
Georgia with red highlights.

![Screenshot of the Royal theme](/media/royal.jpg)

### Candy
Soft pink background and highlights, Avenir.

![Screenshot of the Candy theme](/media/candy.jpg)



## Layout Gallery

Layouts control how Drops in your Stream are laid out, think of them as the structural customization vs. the ornamental features provided by themes. 

You can, of course, mix-and-match themes and layouts. The layouts here all use the Classic theme for consistency, but they look much cooler with the other themes, if you ask me.

### Classic
Horizontal on desktop, squeezes in from there. 
![Screenshot of the Classic layout](/media/classic.png)

### Feed
Half the width, twice the scroll.
![Screenshot of the Feed layout](/media/feed.png)

### Wall
Pinterest-sytle bricks in a wall.
![Screenshot of the Wall layout](/media/wall.png)

### Newspaper
Dense text, triple columns.
![Screenshot of the Newspaper layout](/media/newspaper.png)



## Roadmap

If you don't see something here that you'd really like, feel free to tell me about it. 

- Link to other people's streams
- Set your own favicon
- Get it to work with channels (would enable collaborative streams)
- Internal linking
- A formal tagging system
- Custom domains
- Multiple streams
- Semantic search
- Table of contents 

**Note:** Some of these might become paid features.



## Microblogging

Here is a list of great streams/microblogs that could make for good design inspiration:

- [Linus' Stream](https://stream.thesephist.com/)
- [Simon Collison's Stream](https://colly.com/stream)
- [Grant Custer's Feed](https://feed.grantcuster.com/)
- [Snufkin's microblog](https://ocean-waves.xyz/microblog/)
- [The DazeEnd microblog](https://microblog.dazeend.org/)
- [Chris Krycho's Atomic](https://v1.microblog.chriskrycho.com/)
- [Brandur's Atoms](https://brandur.org/atoms)
- [Ake's µnotes](https://ake.neocities.org/ublog)
- [Tim Brown's Thoughts](https://tbrown.org/feed.thoughts.xml)
- [Wide Gamut](https://redalemeden.com/microblog)



## Furthermore...

There are a few small details that need to be ironed out:

- Editing a Drop that has an image works fine if you only change the caption text, but trying to change the media itself will not do anything at the moment.

- Since Telegram limits the edit to feature only to messages that are less than 48 hours old.

- Currently, the bot only renders iframe embeds from a few specific websites, if you want to embed something that isn't on this list, let me know and I'll add it. 

    | Website | Allowed URLs |
|-|-|
| Youtube | www.youtube.com |
| Spotify | open.spotify.com |
| Vimeo | www.vimeo.com, player.vimeo.com |
| Google | docs.google.com, drive.google.com, www.google.com |
| Soundcloud | w.soundcloud.com |
| DailyMotion | www.dailymotion.com, dailymotion.com|
| Facebook | www.facebook.com, facebook.com |
| Pinterest | www.pinterest.com |
| Twitch | player.twitch.tv |
| Tumblr | www.tumblr.com |
| Instagram | www.instagram.com |
    
    **Note:** Twitter is unsupported because their emebeds do not use an `<iframe>`, but Javascript-based rendering.  


## Gratitude

*Thanks to [evgenii](https://twitter.com/gene_minkov), [Abhimanyu](https://twitter.com/A_Bhimany_u), [nvpkv](https://twitter.com/nvpkv), [daytura](https://twitter.com/ArchLeucoryx), [Cam](https://twitter.com/Empathy2000), [gobborg](https://twitter.com/tamalefencer), [nobu](https://twitter.com/nobu_hibiki), and [Nihal](https://twitter.com/annihalated) for their excellent suggestions, encouragement and critique. And to [Kai](https://twitter.com/kaisoapbox) for writing the first (and only) $100 cheque.*