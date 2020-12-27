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

### Android

The latest release of Firefox makes adding extensions a little more difficult (and that's an understatement). If you'd like to do so, follow these steps:

1. Download Firefox Nightly from the Play Store
2. Go into the settings and click on `About Firefox Nightly` at the bottom of the settings menu
3. Tap on the Firefox logo until it enables the debug mode
4. Go back into settings and click on `Custom Add-on collection`
5. Type the following information in the dialog:
* Collection owner: `15736936`
* Collection name: `YTDL-M`
6. Add the extension
7. Go back to settings and click `Addons` then `YoutubeDL-Material` and set up the settings for the extension
8. You're all set! Navigate to a YouTube page, click the 3 dots on the bottom right, then click Addons, and then click YoutubeDL-Material to start your download.