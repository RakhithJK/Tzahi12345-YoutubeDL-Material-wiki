# Overview

[API Docs](https://stoplight.io/p/docs/gh/tzahi12345/youtubedl-material?group=master&utm_campaign=publish_dialog&utm_source=studio)

To get started, go to the settings menu and enable the public API from the *Extra* tab. You can generate an API key if one is missing.

Once you have enabled the API and have the key, you can start sending requests by adding the query param `apiKey=API_KEY`. Replace `API_KEY` with your actual API key, and you should be good to go! Nearly all of the backend should be at your disposal.

View all available endpoints in the link above.

# Examples

## Downloading files

### Downloading audio files 
    curl -XPOST -H "Content-type: application/json" -d '{"url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ"}' 'http://localhost:17442/api/tomp3?apiKey=YOUR_API_KEY'

### Downloading video files
    curl -XPOST -H "Content-type: application/json" -d '{"url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ"}' 'http://localhost:17442/api/tomp4?apiKey=YOUR_API_KEY'

## Getting files

### Get all MP3 files
    curl -XPOST -H "Content-type: application/json" -d '{}' 'http://localhost:17442/api/getMp3s?apiKey=YOUR_API_KEY'

The resulting object will have a key `mp3s` that contains an array of all `mp3` files located in your audio files directory. It will also have all of the available audio playlists under the `playlist` key.

### Get all MP4 files
    curl -XPOST -H "Content-type: application/json" -d '{}' 'http://localhost:17442/api/getMp4s?apiKey=YOUR_API_KEY'

The resulting object will have a key `mp4s` that contains an array of all `mp4` files located in your video files directory. It will also have all of the available video playlists under the `playlist` key.

## Subscriptions

    curl -XPOST -H "Content-type: application/json" -d '{"url": "https://www.youtube.com/channel/UCuAXFkgsw1L7xaCfnd5JJOw"}' 'http://localhost:17442/api/subscribe?apiKey=YOUR_API_KEY'`

You can also add optional `name` and `timerange` parameters to the object to specify a custom name and a custom timerange to download videos from (see available ones [here](https://github.com/ytdl-org/youtube-dl/blob/master/README.md#video-selection-1)) for the subscription.