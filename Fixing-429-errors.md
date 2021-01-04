## Explanation

429 errors come about when YouTube or other sites decide you've downloaded too much content in a short period of time. There are a few ways to solve this once you get the error, but one way to reduce the frequency of these errors is by increasing the subscription check interval. By default it's 5 minutes, if you set it to 1 hour for example the errors will be much less frequent.

## Methods to get rid of the error

1. Use the cookies uploader in the settings to upload a `cookies.txt` file of your YouTube cookies. [Here's a guide](https://apple.stackexchange.com/a/349759) that will help you download them. TLDR is you can either do it manually (slowly) or use this [Chrome browser extension](https://chrome.google.com/webstore/detail/get-cookiestxt/bgaddhkoddajcdgocldbbfleckgcbcid?hl=en). Once you have the txt file, upload it using the aforementioned dialog in the `Advanced tab` in the settings menu.

2. Add the `--proxy` arg to your global custom args in the settings. Here's [an example](https://stackoverflow.com/a/42948404/8088021). If that doesn't work and you're using Docker, try the [docker-compose method](https://github.com/Tzahi12345/YoutubeDL-Material/issues/177#issuecomment-722685712).

3. Wait a day or so for YouTube to unblock your IP.

### Additional solutions

* [Suggestions from youtube-dl repo](https://github.com/ytdl-org/youtube-dl#http-error-429-too-many-requests-or-402-payment-required)
* Add `--sleep-interval,,60` arg to your custom args in your subscription which will cause each video to get downloaded with a delay of 60 seconds