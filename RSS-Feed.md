## Intro

With v4.3.1, you can now easily generate an unlimited amount of RSS feeds of your downloaded videos. You can filter by a number of fields:
* Title
* File type (video, audio, both)
* User ID
* Subscription
* Only favorites

You can also limit the number of downloads you'd like to appear, in case you have a lot of them.

## Generating a link

### Auto (easy)

To generate an RSS feed link, first enable it in the `Extra` tab of the settings menu. Then click "Generate RSS URL" and fill in the fields to begin generating the URL.

### Manual

You can also generate the RSS feed URL manually by utilizing the `/api/rss` API endpoint, but note that some fields (sort, text_search if using regex) may require URI encoding.

Link: coming soon!

## Example

http://example.com/api/rss
* Generate feed with files downloaded in single-user mode

http://example.com/api/rss?uid=admin
* Generate feed with files downloaded by user `admin`

http://example.com/api/rss?uid=admin&text_search=chess
* Generate feed with files downloaded by user `admin`, and filter for files that include the word `chess`

http://example.com/api/rss?sub_id=abcd
* Generate feed with files from subscription with ID `abcd`

## Links

Helpful validator: https://validator.w3.org/feed/check.cgi

Pretty web-based viewer: https://rssviewer.app/