# StayMarta Local Development Environment

This repo contains everything you need to start hacking on the StayMarta backend!

## Setup

### Prerequisites

* [docker-machine](https://docs.docker.com/machine/install-machine/)
* [curl](https://curl.haxx.se/)
* [VirtualBox 5.x](https://www.virtualbox.org/)
* [docker](https://docker.io) EXCEPT Mac, see below.

#### Mac

The setup script can install `docker-machine` and `brew`.

* [Docker for Mac](https://docs.docker.com/engine/installation/mac/)
* [Homebrew](http://brew.sh/)

#### Windows

not supported yet...

### Install

```bash

$ setup.sh
```

... and you're done!

Rancher will be accessible at http://127.0.0.1:8080.

## Things to come...

* Build Pipeline intergration
* Quick Deploys to Development
* Automatic Rancher Snapshots *from* production.

## Reporting Errors

Please attach a full log, and the output of a couple of commands:

`docker-machine ls`

`docker ps`

These commands will help us debug issues much faster!

## Services

Jenkins is running on: `192.168.99.10`

## License

BSD-3-Clause
