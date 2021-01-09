## Introduction

Categories are a way to categorize your videos based on a set of rules. These can be ANDed or ORed, meaning you can customize the rules to your liking.

## What can they do?

Right now, not a *ton* of features exist for categories, but it's something that will be built upon in the future. There are two features implement currently which may make it worthwhile:

* Custom file output
  * Your categorized videos may be placed in any folder in your filesystem, so absolute paths are possible here -- and it supports youtube-dl's file output features allowing you to customize the file name to your choosing for that specific category
* Automatic playlists
  * If one or multiple videos exist in a category, it gets automatically created into a playlist which will show up on your home screen

## Example

For example, if you want a "tech" category, you can have the following ruleset:

<img src="https://i.imgur.com/oTjo1NE.png" width="500">

And let's say you want a custom file output for these videos, you can make it `videos/tech/%(title)s`, meaning all those videos will end up in a folder called `tech` in your `videos` folder.