---
title: 'The [streams.place](https://streams.place) API'
description: "API • Streams"
---

<div id="menu">
    <ul>     
        <li><a href="#authentication"> Authentication </a></li>
		<li> <a href="#get-route-usernamejson"> GET route </a>
		<li> <a href="#post-route-usernameapipost"> POST route </a>
    </ul>
</div>


Learn how to use the simple REST endpoints to fetch Drops to display on your own front-end, or post a new Drop from outside of Telegram.


## Authentication 

The GET endpoint requires no authentication and is available directly at the `username/json` route. It only returns a list of your public Drops, private ones stay protected.

For POST requests, your keyphrase is required to be added to the header of your request as an authentication method.

## GET route (username/json) 

Returns an array of all the user's public Drops. Each element of the array corresponds to one Drop and has the following properties

| Property | Contents | Example |
|-|-|-|
| **timestamp** | UNIX-style timestamp for when the Drop was created | `1681908281288` |
| **id** | A (shortened) UUID number for a Drop | `MjZlNTgxMjAt` |
| **html** | HTML representation of the Drop's contents, as rendered by the bot | `"<p>If you can see this message, it means that the POST endpoint works…</p>\n"` |
| **text** | The raw text that the bot recieved from Telegram | `"If you can see this message, it means that the POST endpoint works..."` |
| **last_edit** | UNIX-style timestamp for when the Drop was last edited | `1680172933000` |
| **media** | An array of objects representing media associated with a drop | `[]` (empty because no media) |

There are three types of media objects that the `media` array might contain:

#### I. photo

```json 
{
    "type":"photo",
    "file_id":"AgACAgUAAxkBAAIOIWQsxhNo_nDpiRUc5YpOZ6WbvU34AAK9tTEbx3xhVaSsb-2Mkd7zAQADAgADeQADLwQ",
    "urlToFile":"https://fvinkehbbprjnyunhwkc.supabase.co/storage/v1/object/public/stream-images/beta/AgACAgUAAxkBAAIOIWQsxhNo_nDpiRUc5YpOZ6WbvU34AAK9tTEbx3xhVaSsb-2Mkd7zAQADAgADeQADLwQ.jpg"
}
```

#### II. animation

```json
{
    "type": "animation",
    "file_name": "mygif.gif",
    "file_id": "AgACAgUAAxkIOWHgngQsxhNo_nDpiRUc5Yp109yt284twnkwshVaSsb-2Mkd7sgsrgADeQADLwQ",
    "urlToFile": "https://fvinkehbbprjnyunhwkc.supabase.co/storage/v1/object/public/stream-images/beta/AgACAgUAAxkIOWHgngQsxhNo_nDpiRUc5Yp109yt284twnkwshVaSsb-2Mkd7sgsrgADeQADLwQ.gif"
}
```

#### III. audio

```json
{
    "type": "audio",
    "file_name": "mysong.mp3",
    "performer": "Judah",
    "title": "My Song",
    "file_id": "AxkIOWHgngQsxhNo_nDpiRUc5Yp109yt284twnkwshVa-eQADLwsrht23tgs",
    "urlToFile": "https://fvinkehbbprjnyunhwkc.supabase.co/storage/v1/object/public/stream-images/beta/AxkIOWHgngQsxhNo_nDpiRUc5Yp109yt284twnkwshVa-eQADLwsrht23tgs.ogg"
}
```

#### Example payload
To bring it all together, here's an example response from a Stream that contains three Drops, one of which has a photo attached.

```json
[
	{
		 "timestamp": "1681908281288",
		 "id": "MjZlNTgxMjAt", 
		 "html": "",
		 "text": "",
		 "last_edit": "",
		 "media": []
	},

	{
		 "timestamp": "1681908220941",
		 "id": "192jWiE9jneX", 
		 "html": "",
		 "text": "",
		 "last_edit": "",
		 "media": []
	},

	{
		 "timestamp": "1681901303130",
		 "id": "I093IE139jrn", 
		 "html": "",
		 "text": "",
		 "last_edit": "",
		 "media": [
			{
			    "type":"photo",
			    "file_id":"AgACAgUAAxkBAAIOIWQsxhNo_nDpiRUc5YpOZ6WbvU34AAK9tTEbx3xhVaSsb-2Mkd7zAQADAgADeQADLwQ",
			    "urlToFile":"https://fvinkehbbprjnyunhwkc.supabase.co/storage/v1/object/public/stream-images/beta/AgACAgUAAxkBAAIOIWQsxhNo_nDpiRUc5YpOZ6WbvU34AAK9tTEbx3xhVaSsb-2Mkd7zAQADAgADeQADLwQ.jpg"
			}
		]
	}
]
```

You can use the JSON to render your Stream to your own site, or create your own copy of your data. 

## POST route (username/api/post)

***Note:** This endpoint has a rate-limit of 20 posts per minute.*

Accepts a text string to store as a new Drop. If `process_as_markdown` is set to `true`, the bot processes any markdown characters in the text to HTML. 

The `keyphrase` entry to your headers object with your keyphrase as the value. The text for the new Drop should be added to a `message` entry in the request body.

**Example POST request:**

```javascript
fetch('https://streams.place/judah/api/post',
    {
    method: "POST",
    body: JSON.stringify({
        // This is the text of your post, markdown formatting is optional, of course. 
        message: `## This is a markdown formatted message.
        It's pretty **cool** to be able to do this, no?`,
        // This informs the bot that it should render this text as Markdown. (default: true)
        process_as_markdown: true
    }),
    headers: {
        "Content-Type": "application/json",
        // Add your own keyphrase instead of 'your-great-code'
        "keyphrase": "your-great-code"
    }

    }).then((response) => {
        if (response.ok) {
            return response.json();
        }
        throw new Error('Something went wrong');

    }).then((responseJson) => {
        console.log(responseJson)
        // responseJson = {success: true} if the request worked

    }).catch((error) => {
        console.log(error)
    });
```

If the request was successful, you should recieve a JSON payload with the `success` value set to `true`. If not, a value of `false` will return instead, along with a `message` value that informs you why the request failed. 

#### I. Username is not being used by any existing users.

```json
{ 
	"success": false, 
	"message": "Incorrect username. That user does not exist."
}
```
Please ensure that you are using the correct username (the sub-URL your Stream is located at). Example: if my Stream is located at https://streams.place/judah, my username is `judah`.

You can change your username with the /newusername command.


#### II. Keyprase did not match [username]'s keyphrase.

```json
{ 
	"success": false, 
	"message": "Incorrect keyphrase. Go away."
}
```
Please make sure your keyphrase is correct, use the /keyphrase command to check your current keyphrase.


#### III. Something broke on the server. 

```json
{ 
	"success": false, 
	"message": "ERROR 500: Something went wrong."
}
```
If you aren't trying something evil, this is probably my fault. Try again, and let me know if the error persists.
