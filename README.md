docker-gogs
===========

Dockerfile for [gogs](http://gogs.io) server(a self-hosted git service).  Supporting SQLite and HTTP.

## Usage
```
docker pull angryegret/docker-gogs

mkdir -p /var/gogs
docker run --name=gogs -d -p 10022:22 -p 10080:3000 -v /var/gogs:/data angryegret/docker-gogs
```

Open bowser and naviage to

```
http://yourhost:10080
```

It's ok to change `/var/gogs` to another directory.

Directory `/var/gogs` keeps git and gogs data

	/var/gogs
	├── git
	│   └── gogs-repositories
	|-- ssh
	|    `-- # ssh pub-pri keys for gogs
	└── gogs
		├── conf
		├── data
		├── log
		└── templates

Config file is in `gogs/conf/app.ini`

If your store engine choose sqlite, then the data file is in `gogs/data/gogs.db`
