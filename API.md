# API

You can use the internal API on your server to run downloads on your instance without using the frontend. All of the available endpoints can be seen over [here](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/backend/app.js) -- search for '/api/' on the page to find all the endpoints. 

Note that in the future, the API will be updated such that it can be accessed outside of your network, and will be more documented both internally and in this very wiki page.

## Downloading files

### Downloading audio files 
`curl -XPOST -H "Content-type: application/json" -d '{"url": "<your video url>"}' 'http://localhost:17442/api/tomp3'`

Remember to replace `<your video url>` with the actual URL. 

### Downloading video files
`curl -XPOST -H "Content-type: application/json" -d '{"url": "<your video url>"}' 'http://localhost:17442/api/tomp4'`

Remember to replace `<your video url>` with the actual URL. 

## Getting files

### Get all MP3 files
`curl -XPOST -H "Content-type: application/json" -d '{}' 'http://localhost:17442/api/getMp3s'`

The resulting object will have a key `mp3s` that contains an array of all `mp3` files located in your audio files directory. It will also have all of the available audio playlists under the `playlist` key.

### Get all MP4 files
`curl -XPOST -H "Content-type: application/json" -d '{}' 'http://localhost:17442/api/getMp4s'`

The resulting object will have a key `mp4s` that contains an array of all `mp4` files located in your video files directory. It will also have all of the available video playlists under the `playlist` key.

## Subscriptions

`curl -XPOST -H "Content-type: application/json" -d '{"url": "<channel or playlist url>"}' 'http://localhost:17442/api/subscribe'`

You can also add optional `name` and `timerange` parameters to the object to specify a custom name and a custom timerange to download videos from (see available ones [here](https://github.com/ytdl-org/youtube-dl/blob/master/README.md#video-selection-1)) for the subscription.