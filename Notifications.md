# Introduction

With v4.3.1, there is now notifications support. There are built-in notifications in the UI where you can interact with the alerts, and there's third party integrations. This wiki page primarily focuses on the latter.

Go to the `Notifications` tab in your settings to integrate with:

* [Telegram](https://telegram.org/)
* [Gotify](https://gotify.net/)
* [ntfy](https://ntfy.sh/)
* Any service that supports custom webhooks! This includes [Zapier](https://zapier.com/) and [Automatisch](https://automatisch.io/)

There are currently 3 types of notifications. Here they are and the type of data you'll get:

* Download complete
  * Included data: video title, original URL, new URL (on your instance), thumbnail
* Download error
  * Included data: error type, original URL
* Task finished
  * Included data: task title

You can disable or enable each type of notification to your choosing.

# Get started

## Telegram

For Telegram, you will need two things: a bot token and a chat ID

* To get a bot token, create a bot using [BotFather](https://telegram.me/botfather)
  * Type `/newbot` and follow the instructions
  * Copy the generated token into the `Telegram bot token` setting
* Get your chat ID using the [get id bot](https://telegram.me/get_id_bot)
  * You can get your ID by typing `/my_id`

## Gotify

Docs: https://gotify.net/

For Gotify you will need the server URL, as well as an app token. You can generate the app token from Gotify's web UI

## ntfy

Docs: https://docs.ntfy.sh/

All you need is the topic URL! 

You can test out the functionality by going to the demo site and creating a topic: https://ntfy.sh/app

## Custom webhook

Paste the URL, which could be retrieved from a third party service like [Zapier](https://zapier.com/) or [Automatisch](https://automatisch.io/). Here's the format of the data you will get in the body of the POST:

```
{
    body: <general message>,
    title: <notification title>,
    type: <notification type>,
    url: <relevant url to your instance>,
    thumbnail: <video thumbnail if present>
}
```

Three notification types:
* download_complete
* download_error
* task_finished

Here's an example of a download error notification:

```
{
    body: "Error: exists_in_archive\nURL: https://www.youtube.com/watch?v=example_id"
    title: "Download error"
    type: "download_error"
    url: "http://127.0.0.1:17442/#/downloads"
    thumbnail: null
}
```