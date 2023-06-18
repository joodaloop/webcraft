---
title: 'The FAQ'
description: "FAQ • Streams"
---

## Can I quote/thread/link my Drops?

No quotes, in the sense of quotetweeting. There's no threading either, because you can just edit your Drop to add more words (until Telegram's 48-hour edit limit ends).

You can however, link to Drops in two ways. The first is in-page linking, where clicking on a link will scroll down to the linked Drop. In-page links are located in the "Date" section of your Drops.

Permalinks for Drops also exist, in the form of a unique *streams.place/username/drops/drop-id* link for each one. Those are found in the "Time" section of the Drop.

### Why don't Streams also have a web dashboard to edit/delete posts?

Because the point of a Stream is low-friction, minimal effort posts. I want you to show your rough work, your [outtakes and footnotes](https://twitter.com/visakanv/status/1647013871247593477). The need to log in, visit a website, click different buttons, etc. are all obstacles to *just posting*.

If you're using a Stream, it's best to accept the light, unserious nature of the medium from the get-go. Posting here should feel effortless. If it feels like you're fighting the UI, it's probably better for you to export your data and try someplace else.

If you just want to create a minimal blog, check out [bear.blog](https://bear.blog). If you want a regular microblogging platform, check out [micro.blog](https://micro.blog) or [Bluesky](https://bsky.app). 

### Why isn't there support for videos?

I don't want to pay to host really large media files. The site allows media embeds (including YouTube and Vimeo), you can always use those to add videos. Or you can convert videos to GIFs, the bot accepts those.  

### What’s the encryption and security of how data goes from my Telegram chat to my Stream?

Data is stored on Telegram's servers, and then sent to the bot, which lives on a Digital Ocean droplet. Encryption and security are taken care of by Telegram and the bot's token.  

### Can Streams be made private?

No, but you can hide specific Drops from your public Stream by using the [/protect](/commands#protect) command, just reply to a Drop with /protect. Your private Stream (including protected Drops) is available on a private page (your-url/keyphrase).

However, if you *really* want to hide your entire Stream, just changing your username to a long, weird string will probably be enough to make sure nobody will find it.

<!-- ### Can I add my Stream to my own site?

There are two ways to do this. 

The simpler way is to add an `<iframe>` element to your page, with it's `src` attribute set to your Stream's URL. Below is a snippet that you can just copy-paste into a webpage after changing the "[username]" in the src to your own username.

```html
<iframe src="https://streams.place/[username]"></iframe>
```

If you're more technical, you can also use the [API](/api) to fetch your Drops as JSON and render them on your own site. -->


### Is this free? How? Why?

Yes, it is. Firstly, becasue it was fairly easy to build, just under month of work. Second, at the moment, it costs me close to nothing to keep it running. 

However, "close to nothing" doesn't mean $0. Labour, servers and domains aren't exactly free. And so you can, of course, choose to send me money if you feel like it.

### Will it always be free?

*Always* is a strong word. I'm not even sure how long Telegram will be around for. But all your data is stored in it's original format and will be avilable to export whenever you wish to do so. 

It's possible that there will one day be a paid tier that will provide things like higher quality images, video hosting, etc. But the most important bits will be free. 

### What did you use to make this?

The bot runs on a DigitalOcean droplet, and listens for messages that are then stored in a PostgresDB and S3 Bucket on Supabase. It uses the excellent [Telegraf](https://telegrafjs.org) and [Marked](https://marked.js.org) libraries within an ExpressJS server. 

Like all my projects, the front-end is plain ol' HTML+CSS, with full-text search being provided by a simple JavaScript function. I plan to make the code for recieving and processing markdown-formatted mesages from a Telegram open-source soon. 


