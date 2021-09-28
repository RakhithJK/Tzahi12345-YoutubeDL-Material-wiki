# Introduction

The configuration is stored in `appdata` directory. It's a JSON file separated into several categories and defines behavior for the app. [See the latest version here.](https://github.com/Tzahi12345/YoutubeDL-Material/blob/master/backend/appdata/default.json).

# Items

| Text | Default.json Path | Key/ENV Var | Explanation | Tab in settings | Default value |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| URL | Host.url | ytdl_url | URL for the frontend - not always needed especially with Docker | Main | http://example.com |
| Port | Host.port | ytdl_port | Port for the frontend | Main | 17442 |
| Audio path | Downloader.path-audio | ytdl_audio_folder_path | Deprecated - not used | Downloader | "audio" |
| Video path | Downloader.path-video | ytdl_video_folder_path | Deprecated - not used | Downloader | "video" |
| Default file output | Downloader.default_file_output | ytdl_default_file_output | Changes the formatting for file names based on [youtube-dl's output template](https://github.com/ytdl-org/youtube-dl/blob/master/README.md#output-template) | Downloader | "" |
| Use youtube-dl archive | Downloader.use_youtubedl_archive | ytdl_use_youtubedl_archive | Creates and uses [archive text files](https://github.com/ytdl-org/youtube-dl/blob/master/README.md#how-do-i-download-only-new-videos-from-a-playlist) to avoid redownloading the same file, and helps track/port already downloaded files | Downloader | false |
| Global custom args | Downloader.custom_args | ytdl_custom_args | youtube-dl args that get added to every download | Downloader | "" |
| Safe download override | Downloader.safe_download_override | ytdl_safe_download_override | Deprecated - not used | N/A | false |
| Include thumbnail | Downloader.include_thumbnail | ytdl_include_thumbnail | Downloads thumbnail along with file | Downloader | true |
| Text | Downloader.include_metadata | ytdl_include_metadata | Downloads [.info.json files](https://github.com/ytdl-org/youtube-dl#filesystem-options) along with file (highly recommended) | Downloader | true |
| Max concurrent downloads | Downloader.max_concurrent_downloads | ytdl_max_concurrent_downloads | Limits the number of simultaneous downloads | Downloader | 5 |
| Download rate limit | Downloader.download_rate_limit | ytdl_download_rate_limit | Limits download speed | Downloader | "" |