![](https://img.shields.io/amo/dw/youtubedl-material)

# Setup

Getting started with the Firefox extension is quite simple!

1. Go to the extension page [here](https://addons.mozilla.org/en-US/firefox/addon/youtubedl-material/) and add the extension.

2. Open the addons menu in Firefox (Ctrl+Shift+A) and open the YoutubeDL-Material options.

3. Modify the frontend URL to match the frontend URL of your instance. Click save.

4. You're all set! Go to a YouTube page and click the icon to automatically start the download.

# What the extension does

### Main function

You can view the source code for the extension's main function [here](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/chrome-extension/background.js).

Basically, it simply uses your browser's tab's URL to redirect you to a YoutubeDL-Material link that will start an automatic download.

As a result, the addon requires the `tabs` permission.

### Cookies

The YoutubeDL-Material link the addon uses is stored in the settings. These settings are stored using your browser's cookies. As a result, the addon requires the `storage` permission. View the settings JS code [here](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/chrome-extension/options.js), and HTML code [here](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/chrome-extension/options.html).