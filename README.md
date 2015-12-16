### Irssi Docker Container
[![GitHub](http://img.shields.io/badge/github-zuazo/irssi--docker-blue.svg?style=flat)](https://github.com/zuazo/irssi-docker) [![ImageLayers Size](https://img.shields.io/imagelayers/image-size/zuazo/irssi/latest.svg)](https://imagelayers.io/?images=zuazo/irssi:latest) [![Docker Repository on Quay.io](https://quay.io/repository/zuazo/irssi/status 'Docker Repository on Quay.io')](https://quay.io/repository/zuazo/irssi) [![Build Status](http://img.shields.io/travis/zuazo/irssi-docker.svg?style=flat)](https://travis-ci.org/zuazo/irssi-docker)

A minimal [Docker](https://www.docker.com/) image (~9 MB) with [Irssi](https://irssi.org/).

#### Supported Tags and Respective `Dockerfile` Links

- `latest` ([*/Dockerfile*](https://github.com/zuazo/irssi-docker/tree/master/Dockerfile))

#### What Is Irssi?

Irssi is a terminal based IRC client for UNIX systems. It also supports SILC and ICB protocols via plugins. Some people refer to it as *the client of the future*.

> [irssi.org](http://irssi.org)

[![Irssi Logo](https://raw.githubusercontent.com/zuazo/irssi-docker/master/logo.png)](https://irssi.org/)

#### How to Use This Image

##### Download the Image

    $ docker pull zuazo/irssi

##### Run Irssi

    $ docker run zuazo/irssi

##### Passing Options to Irssi

    $ docker run -ti zuazo/irssi \
      -c irc. freenode.net -p 6667 \
      -n MYNICK -w MYPASS

##### Adding Your Own Startup File

```Dockerfile
FROM zuazo/irssi

COPY etc/startup $IRSSI_CONF_DIR/startup
```

##### Adding Your Own Scripts

```Dockerfile
FROM zuazo/irssi

COPY scripts/myscript.pl $IRSSI_SCRIPTS_DIR/myscript.pl
```

##### Using Irssi with Tor

See the [`irssi-tor`](https://hub.docker.com/r/zuazo/irssi-tor/) image.

#### Build from Sources

Instead of installing the image from Docker Hub, you can build the image from sources if you prefer:

    $ git clone https://github.com/zuazo/irssi-docker irssi
    $ cd irssi
    $ docker build -t zuazo/irssi .

#### Read-only Environment Variables Used at Build Time

- `IRSSI_HOME`: Irssi user home directory.
- `IRSSI_CONF_DIR`: Irssi configuration directory.
- `IRSSI_SCRIPTS_DIR`: Directory where you can add your Irssi scripts.
