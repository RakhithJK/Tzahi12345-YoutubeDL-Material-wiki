NOTE: This may apply for older Raspberry Pi's as well.

# Docker

You may see the following error appear:

```
ytdlt-db-1  | 
ytdlt-db-1  | WARNING: MongoDB 5.0+ requires ARMv8.2-A or higher, and your current system does not appear to implement any of the common features for that!
ytdlt-db-1  |   see https://jira.mongodb.org/browse/SERVER-55178
ytdlt-db-1  |   see also https://en.wikichip.org/wiki/arm/armv8#ARMv8_Extensions_and_Processor_Features
ytdlt-db-1  |   see also https://github.com/docker-library/mongo/issues/485#issuecomment-970864306
ytdlt-db-1  | 
ytdlt-db-1 exited with code 132

```

MongoDB's latest Docker image does not support Raspberry Pi 4.

The workaround is to set the MongoDB version in the docker-compose to `4.4.18` like so:

```
image: mongo:4.4.18
```

So your full docker-compose.yml may look like this:

```
version: "2"
services:
    ytdl_material:
        environment: 
            ALLOW_CONFIG_MUTATIONS: 'true'
            ytdl_mongodb_connection_string: 'mongodb://ytdl-mongo-db:27017'
            ytdl_use_local_db: 'false'
            write_ytdl_config: 'true'
        restart: always
        volumes:
            - ./appdata:/app/appdata
            - ./audio:/app/audio
            - ./video:/app/video
            - ./subscriptions:/app/subscriptions
            - ./users:/app/users
        ports:
            - "8998:17442"
        image: tzahi12345/youtubedl-material:latest
    ytdl-mongo-db:
        image: mongo:4.4.18
        ports:
            - "27017:27017"
        logging:
            driver: "none"          
        container_name: mongo-db
        restart: always
        volumes:
            - ./db/:/data/db
```

## References

* https://github.com/Tzahi12345/YoutubeDL-Material/issues/614#issuecomment-1142216713
* https://jira.mongodb.org/browse/DOCS-14684
* https://github.com/docker-library/mongo/issues/485
* https://www.mongodb.com/community/forums/t/mongodb-5-0-cpu-intel-g4650-compatibility/116610
* https://www.mongodb.com/community/forums/t/core-dump-on-mongodb-5-0-on-rpi-4/115291