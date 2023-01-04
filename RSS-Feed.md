Placeholder for where future documentation will exist.

Helpful validator: https://validator.w3.org/feed/check.cgi

Prettier web-based viewer: https://rssviewer.app/

Examples:

<URL>/api/rss
* Generate feed with files downloaded in single-user mode

<URL>/api/rss?uid=admin
* Generate feed with files downloaded by user `admin`

<URL>/api/rss?uid=admin&text_search=chess
* Generate feed with files downloaded by user `admin`, and filter for files that include the word `chess`

<URL>/api/rss?sub_id=<sub id>
* Generate feed with files from subscription with ID `<sub id>`