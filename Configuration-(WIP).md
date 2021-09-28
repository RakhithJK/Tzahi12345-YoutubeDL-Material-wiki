# Introduction

The configuration is stored in `appdata` directory. It's a JSON file separated into several categories and defines behavior for the app. [See the latest version here.](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/backend/appdata/default.json).

# Items

## Main (WIP)

| Text | Name | Key/ENV Var | Explanation | Default value |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| URL | url | ytdl_url | URL for the frontend - not always needed especially with Docker | http://example.com |
| Port | port | ytdl_port | Port for the frontend | 17442 |
| Multi-user mode | multi_user_mode | ytdl_multi_user_mode | Allows creation of users (with their own files), roles, and permissions, enables the `Users` tab | false |
| Users base path | users_base_path | ytdl_users_base_path | Deprecated - not used | "users/" |
| Allow subscriptions | allow_subscriptions | ytdl_allow_subscriptions | Allows subscribing to channels | true |
| Subscriptions base path | subscriptions_base_path | ytdl_subscriptions_base_path | Deprecated - not used | "subscriptions/" |
| Check interval | subscriptions_check_interval | ytdl_subscriptions_check_interval | Amount of time between cycling through all subscriptions. If you have 10 subs and the interval is set to 100, every 10 seconds another sub will be checked | 86400 |
| Redownload fresh uploads | redownload_fresh_uploads | ytdl_subscriptions_redownload_fresh_uploads | Checks day-old or newer videos in a subscription to see if a higher quality one exists. If it does, it's downloaded | false |
| Theme | default_theme | ytdl_default_theme | Sets the default theme ("default" or "dark") | "Default" |
| Allow theme change | allow_theme_change | ytdl_allow_theme_change | Allows the theme to be changed by hitting the 3 dots in the top right corner | true |

## Downloader (finished)

| Text | Name | Key/ENV Var | Explanation | Default value |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| Audio path | path-audio | ytdl_audio_folder_path | Deprecated - not used | "audio" |
| Video path | path-video | ytdl_video_folder_path | Deprecated - not used | "video" |
| Default file output | default_file_output | ytdl_default_file_output | Changes the formatting for file names based on [youtube-dl's output template](https://github.com/ytdl-org/youtube-dl/blob/master/README.md#output-template) | "" |
| Global custom args | custom_args | ytdl_custom_args | youtube-dl args that get added to every download | "" |
| Allow playlist categorization | allow_playlist_categorization | ytdl_allow_playlist_categorization | Playlists get  | 17442 |
| Use youtube-dl archive | use_youtubedl_archive | ytdl_use_youtubedl_archive | Creates and uses [archive text files](https://github.com/ytdl-org/youtube-dl/blob/master/README.md#how-do-i-download-only-new-videos-from-a-playlist) to avoid redownloading the same file, and helps track/port already downloaded files | false |
| Include thumbnail | include_thumbnail | ytdl_include_thumbnail | Downloads thumbnail along with file | true |
| Include metadata | include_metadata | ytdl_include_metadata | Downloads [.info.json files](https://github.com/ytdl-org/youtube-dl#filesystem-options) along with file (highly recommended) | true |
| Max concurrent downloads | max_concurrent_downloads | ytdl_max_concurrent_downloads | Limits the number of simultaneous downloads | 5 |
| Download rate limit | download_rate_limit | ytdl_download_rate_limit | Limits download speed | "" |

## Extra (finished)

| Text | Name | Key/ENV Var | Explanation | Default value |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| Top title | title_top | ytdl_title_top | Sets the top bar and browser tab title | "YoutubeDL-Material" |
| File manager enabled | file_manager_enabled | ytdl_file_manager_enabled | Enables file management in the home screen | true |
| Downloads manager enabled | enable_downloads_manager | ytdl_enable_downloads_manager | Enables download management page | true |
| Allow quality select | allow_quality_select | ytdl_allow_quality_select | Allows changing quality of files (resolution/bitrate). Disabling this means it's always the best quality selected. | true |
| Download only mode | download_only_mode | ytdl_download_only_mode | Playing videos is disabled, they can only be downloaded | false |
| Enable public API | use_API_key | ytdl_use_api_key | Allows [YoutubeDL-Material's API](https://github.com/Tzahi12345/YoutubeDL-Material#api) to be utilized | false |
| Public API Key | API_key | ytdl_api_key | Key used to authenticate YoutubeDL-Material's API users | "" |
| Use YouTube API | use_youtube_API | ytdl_use_youtube_api | Enables YT API use, currently only used for searching for videos through the URL bar | false |
| Youtube API Key | youtube_API_key | ytdl_youtube_api_key | YT API Key ([instructions to generate](https://developers.google.com/youtube/v3/getting-started)) | "" |
| Use Twitch API | use_twitch_API | ytdl_use_twitch_api | Enables Twitch API use, currently only used for downloading chats for VODs | false |
| Twitch API Key | twitch_API_key | ytdl_twitch_api_key | Twitch API Key ([instructions to generate](https://dev.twitch.tv/docs/api/)) | "" |
| Auto-download Twitch Chat | twitch_auto_download_chat | ytdl_twitch_auto_download_chat | Automatically downloads Twitch chats for VODs (requires Twitch API to be enabled) | false |
| Use SponsorBlock API | use_sponsorblock_API | ytdl_use_sponsorblock_api | Enables "Skip ads" button in the video player if found on [SponsorBlock](https://sponsor.ajay.app/) | false |
| Generate NFO files | generate_NFO_files | ytdl_generate_nfo_files | Automatically creates [NFO files](https://kodi.wiki/view/NFO_files) for downloaded videos, primarily used with Kodi | false |