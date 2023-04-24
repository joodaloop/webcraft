---
title: 'Commands cheatsheet'
description: "Commands - streams.place"

---

<div id="menu">
    <ul>     
    	<li> <a href="#about"> /about </a>
        <li><a href="#clean"> /clean </a></li>
        <li><a href="#delete"> /delete </a></li>
        <li><a href="#editor"> /editor </a></li>
        <li><a href="#export"> /export </a></li>
        <li><a href="#faq"> /faq </a></li>
        <li><a href="#info"> /info </a></li>
        <li><a href="#keyphrase"> /keyphrase </a></li>
        <li><a href="#layout"> /layout </a></li>
        <li><a href="#mydrops"> /mydrops </a></li>
        <li><a href="#newusername"> /newusername </a></li>
        <li><a href="#protect"> /protect </a></li>
        <li><a href="#recover"> /recover </a></li>
        <li><a href="#rss"> /rss </a></li>
        <li><a href="#title"> /title </a></li>
        <li><a href="#theme"> /theme </a></li>
        <li><a href="#unprotect"> /unprotect </a></li>
        <li><a href="#url"> /url </a></li>
        <li><a href="#delete"> /delete </a></li>
    </ul>
</div>

A list of all bot commands and what they do.

### /about 
Use this, followed by a description for your page, to craete an About section for your Stream. 

**Example usage:** `/about This is a really cool stream, trust me.`


### /clean
Sometimes, you might delete a Telegram message without first using the /delete command to remove the associated Drop from your Stream. This is when you need to use /clean, followed by the ID of the Drop (which you can get using the [/mydrops](#ymdrops) command), to accomplish what /delete would. 

**Example usage:** `/clean 53901890342400359`


### /delete
Reply to a message with this command to remove it from your Stream. You can delete the message itself, but only *after* you've done this.

### /editor
Returns a link to your theme editor, the page that lets you customise your Stream's style using CSS.

### /export
Returns the URL at which your ready-to-export Markdown data is available.

### /faq
Returns a list of frequent user queries, and their answers. 

### /info 
Will display information about the Streams project, and basuc usage instructions.


### /keyphrase
Returns the three word keyphrase that acts as authentication for private Streams, exports, and the theme-editor.

### /layout
Use this to choose between the available [layouts](/#layout-gallery) for your Stream.

### /mydrops
Returns a list of your last ten Drops, with their associated IDs, usually used with the /clean command.

### /newkeyphrase
Use this command if you want to change your keyphrase. Useful in cases where you feel like the security your keyphrase has been compromised. If you've only forgotten your keyphrase, use the [/keyphrase](#keyphrase) command instead.

### /newusername
Followed by your new username to chage the url location of your stream. Valid usernames need to be lower-case letters, and must not already be in use by another Stream. 

**Example usage:** `/newusername joodaloop`


### /protect
Reply to a Drop with this command to hide it from your public Stream. It will now only be available on your private Stream (your-url/username/keyphrase). Use [/unprotect](#unprotect) to bring it back to the public one.

### /recover
Reply to the Telegram message associated with a deleted Drop to change it's status to undeleted. 

### /rss
Returns a link to your Stream's RSS feed.

### /title
When you create your Stream, your username is used as the title for the Stream's page. Use this command to set your own title. 

**Example usage:** `/title My Cool Stream`


### /theme 
Lets you set a new [theme](/#theme-gallery) for your Stream.

### /unprotect
Reply to a drop with /unprotect to change it's privacy status back to public and have it show up on your public Stream again.

### /url
Returns the URL that your stream is currently located at.


