Running YoutubeDL-Material with a MongoDB database backend will GREATLY increase stability,  
performance and scalability for up to tens of thousands of video/audio downloads  
(as of current testing, tell us if your dataset is larger and successful! :))

Provided you have a MongoDB instance set up (either in a docker or even bare-metal) - you need to  
put the connection string in **Settings > Database > MongoDB Connection String**

&nbsp;&nbsp;&nbsp;&nbsp;![Screenshot 2022-03-25 125507](https://user-images.githubusercontent.com/1912133/160116383-687c2936-b91c-4571-9b49-afd39e072a87.png)

1. _Change the IP and port_ to your MongoDB instance like shown above,
2. click `Test connection string` and if it succeeds...
3. hit `Save`
4. and `Transfer Local to DB`.
(mine says DB to Local because since I already set it up it offers me the other way around)

That's it!

YoutubeDL-Material will create the tables it needs on its own and fill them with the data from your Local DB.  
**This process may take quite some time**, especially on large datasets, so be patient, please! You can use tools  
like MongoDBCompass (MongoDB's official database inspector and editor) to check on the ingress of entries.

<hr>

unRAID specific instructions also available! [Click here](https://github.com/Tzahi12345/YoutubeDL-Material/wiki/unRAID#mongodb-database-setup)