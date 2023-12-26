# Nextcloud User Data Backup

## Installation

```
cd /path/to/this/script
wget https://raw.githubusercontent.com/Dev-Op5/nc-compress/master/nc-compress
```

## Usage

See with `nc-compress help` command:

```
USAGE
   nc-compress <nextcloud-username> <methods>

available <methods>
   rsync             : folder sync (incremental backup) to the BACKUP_BASE_DIR via rsync
   7z                : perform rsync and create compressed .7z backup to the subfolder _backup in BACKUP_BASE_DIR
  <blank>            : same as rsync

<nextcloud-username>
   you can see the list of nextcloud username by run these command:
   occ user:list

PS: you cannot backup the nextcloud data if your nextcloud username is 'help' anyways :-)
```


## Tips

Make this tools available to every user:

```
ln -s /path/to/this/script/nc-compress /usr/local/bin/nc-compress
```

You can create the `/etc/crontab` entry with this line:

```
30 3    * * *   root      /usr/local/bin/nc-compress yournextcloudusername
```

That example above will execute the daily backup every 3:30 AM.
