See a list of config items and their [associated environment variables here](https://github.com/Tzahi12345/YoutubeDL-Material/wiki/Configuration#items).

# ALLOW_CONFIG_MUTATIONS

This is an environment variable for the `node-config` dependency we use. Due to a bug discovered where the config file couldn't be modified on Docker, this was added to fix that. It does not affect any functionality, but removing it may cause errors. 