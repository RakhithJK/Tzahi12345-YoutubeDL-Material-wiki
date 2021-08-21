Please note:
This is a quick write-up of how you can connect mongoDB to YoutubeDL-Material.
There will be more documentation about running YoutubeDL-Material on unRAID in the future, probably once 4.3 releases.

## Introduction
Running YoutubeDL-Material on unRAID at the moment is possible, however there are caveats.
To run a medium-sized database successfully and enjoy the benefits of backing up channels and one-off videos today already we encourage you to try your hand at testing the nightly builds of YoutubeDL-Material on your hardware. unRAID of course not being an exception.

## Limitations
* The application still needs to be more responsive for shutdowns of the app to be graceful at all times.
* The scalability is limited as of now. Whilst you can absolutely run many subscriptions to channels and have a lot of files managed by YoutubeDL-Material, it is VERY advised to run this with a mongoDB connected. A basic setup that assumes you have some level of unRAID knowledge container management already (e.g. adding and editing environment variables in them) is written down below. Even with mongoDB connected the experience still will scale with slowdowns on large databases (e.g. tens of thousands of videos stored), because performance optimizations in the codebase are still needed.

## Recommendations
* If you are going to subscribe to a lot of channels it is very advised that your downloads are writing straight to the array or for your Mover settings to be pretty aggressive, because once your unRAID cache is full it is very possible for things to get very flaky. Especially if your mongoDB is stored on the same cache pool.
* Large installations best use mongoDB as a backend or eventually another dedicated database if/once offered. The default is to use json files in the appdata folder, which is palletable with smaller to medium-sized installations, however things can grow quicker than you expect, especially with subscriptions active. You can also expect a lot better reliability from having a proper database as your backend.

## mongoDB Database Setup
Take the official mongoDB container as posted in the CAs, remove the values from the template for the admin user and password, set networking to host and set the port to your desired value.

Then in ytdl-m (make sure you're on a nightly build that supports mongoDB), do these things:

1. Making backups of the database you have always is a must. Preferably before shutting down the container. Especially pre-mongoDB the database stored in its json files is flakey if you have a large dataset or currently working downloads and/or subs.
2. Go to Settings > Database and set the mongoDB connection string to what the example shows, only that you fill in the IP and port of your mongoDB. We set mongoDB to be host networked, so your unRAID's IP address and the mongoDB port should do.
3. Hit save.
4. Click test connection string. (hitting save was required before testing in a previous nightly build. Not anymore though)
5. If the connection is successful, hit "Transfer DB to mongoDB" or similarly worded (it says "... to Local" for me now, so can't check without ctrl+F'ing into the code, which I'm too lazy to do atm :P)
6. Shut down the container safely
7. I added these keys to my template (I'm using a DIY template, not the one from the CAs, build should work regardless!):
variable 'ytdl_use_local_db' set to false
variable 'write_ytdl_config' set to true
This is probably optional, but that's what I did. So... ymmv