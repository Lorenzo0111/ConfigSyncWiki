---
description: Learn how to configure the plugin.
---

# Configuration

## Scheduler

The scheduler is a task that is automatically scheduled to sync every file every 5 minutes. You can enable and disable it from the configuration file on line 13, the option is named `scheduler`.

## MySQL

The mysql section contains all the data of the database storage. As explained in the configuration, the main server is the one where the files are copied from. NOTE: Don't include the port with your host address, you need to adjust it with the port option. Default value's are:

```yaml
mysql:
  # The main server is the server from the configs are copied
  main: true
  # Database information
  ip: localhost
  port: 3306
  username: "root" #CHANGE THIS TO YOUR DATABASE USER!
  password: "" #CHANGE THIS TO YOUR PASSWORD!
  database: "configsync"
```

## Files

The file section is a list of files to sync. It requires the following schema:

```yaml
files:
  Plugin:
    - "file.yml"
```

Replace `Plugin` with the name of the plugin that contains the file that you want to sync. For example, if you want to sync the `config.yml` of a plugin called `BedwarsX`:

```yaml
files:
  BedwarsX:
    - "config.yml"
```

Add as many files as you want. Instead of the file name you can just put `*` to sync all the files of a plugin.
