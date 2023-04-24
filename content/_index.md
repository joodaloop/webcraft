---
title: "Guide"
description: "Guide • Streams"

---

## About

Streams are [microblogs](#microblogging). The most important feature of a microblog is the freedom from having to add a title to your posts. You can add a short descriptive one, or you can just fire off text into the ether, the choice is yours. 

To add to your Stream, you type out posts as markdown-formatted messages, and the bot renders it within a fully-searchable chronological feed at your own URL. The bot also handles editing (for upto 2 days) and deleting posts. 

You could use it for anything you like, but here's some ideas to get you started. 

- Accountability threads
- Personal log
- Curation
- Daily poetry
- Stream of thoughts
- Worklogs
- Reading logs
- Collections

My own Stream is located at [streams.place/judah](https://streams.place), but I mostly use it for testing purposes when I'm adding a new feature.

I made streams.place because I really liked the idea of Linus' [Stream](https://stream.thesephist.com/), so I built one for my [own site](https://joodaloop.com/stream). Then I wondered if other people might want one too, and how there wasn't really a great way to go about making one. The Telegram API happened to be really simple to work with, so here we are. 

*A blogging platform built on a chat app...*

### I. Create a new post in Telegram

That's all you do, write a minimally-formatted post as a regular Telegram message. The bot confirms the reciept with a message that auto-deletes to prevent your DM getting too cluttered.
![Streams demo, Telegram view](/media/streams-demo-1.gif)


### II. Stream is updated

Refresh your Stream to see the new post, simple as. 
![Streams demo, web view](/media/streams-demo-2.gif)


### III. Edit and delete Drops, right from the chat

Use the native "edit message" feature, and a simple /delete command. You can recover deleted Drops using the /recover command.
![Streams demo, editing and deleting](/media/streams-demo-3.gif)


For more details, and the complete list of commands, check out the [Commands](/commands) page.


## Getting Started

1. Open a new chat with [@text_stream_bot](https://t.me/text_stream_bot).
2. Type in the **/start** command to create an account.
3. Use the **/newusername** command to set your username.
4. Send a message to the bot.
5. Refresh your Stream to see it be rendered as HTML
5. Use the **/info** and **/faq** commands to learn about additional functionality.

## Privacy

In the database, your Stream is associated with your Telegram ID, which is a number that provides me with no private information. Your name, phone number and other profile data remains a secret. 

When you first create your Stream, your Telegram username is used as your username and as the Stream's title. You can easily change this, using the /newusername and /title commands. 

The transferring of messages to my bot is handled by Telegram, with whatever security protocols they have in place for their app as a whole. I can confirm that these message payloads do not contain any private information either. 

If you'd like to erase all trace of your account, [let me know](mailto:judah@joodaloop.com) and I'll get my best agents on the job.


## Features 

Non-exhaustive list of features offered by streams.place. 

| Feature | Details |
|-|-|
| **RSS feed** | Available at *your-url/rss* |
| **API** | GET/POST endpoints, check the [API](/api) page. |
| **Protected drops** | Using the /protect command |
| **Theme editor** | Use the editor at *your-url/editor/your-keyphrase* to create your own themes |
| **Search** | By both date (syntax: year-month-day), and keyword |
| **Export/migration** | The markdown for all your posts is available at *your-url/export/keyphrase* |
| **Storage for images, files and audio** | As long as they are smaller than 2MB | 
| **LaTeX** | Check out the syntax in the [Markdown](#markdown) section |


## Theme Gallery

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

- Since Telegram limits the edit to feature only to messages that are less than 48 hours old, I'm going to have to design an **/edit** command. Sigh.

- Currently, the bot only renders iframe embeds from a few specific websites, if you want to embed something that isn't on this list, let me know and I'll add it. 

    | Website | Allowed URLs |
|-|-|
| Youtube | www.youtube.com |
| Vimeo | |
| Spotify | open.spotify.com |


*Thanks to evgenii, nvpkv, daytura, abhimanyu, cameron, gobborg, nobu, and nihal for suggestions, encouragements and critique. And to Kai for writing the first (and only) $100 cheque.*