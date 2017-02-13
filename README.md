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

#### Controling the Stack

After creation, you have two options:

  * `start.sh` - starts the entire stack
  * `cleanup.sh` - customizable removal of the stack.

## Things to come...

* Build Pipeline integration
* Quick Deploys to Development
* Automatic Rancher Snapshots *from* production.

## Reporting Errors

Please attach a full log, and the output of a couple of commands:

`docker-machine ls`

`docker ps`

These commands will help us debug issues much faster!

## Services

**ALL SERVICES SHARE THE SAME DIRECTORY**

All services has the ability to persist data across git. Simply mount the folder
onto `HOST_MOUNT:IN_CONTAINER` as "/storage/some/path:/path/to/save"

**NOTE**: If you run into permission issues, please run your program with the user
'staymarta' (normally u:501 g:20).

**NOTE**: Be careful to *never* write to `/storage` without a dir included, since you
could overwrite other service('s) data.


## FAQ

### How do I deploy?

Coming soon...

### I don't like rebuilding images!

Simple, just mirror your service to /storage (using rsync, or whatever)

and then write code in the following dir `./storage/<your-dir>`

Then, in container, use something to refresh it on filesystem change.


### How do I add more agents?

`./scripts/create-worker`

## Default Configuration

### Vault

Vault Keys

```
Unseal Key 1: OAXrrc6LY/sXtGQNRce9J0TJjZROjjPxbgRor013uyEB
Unseal Key 2: ee50LwymCG5taKZIrNLSyzfHOf508Xv+XWsBzxDfM+0C
Unseal Key 3: xpEmKTMvSwoBONREwF/JbUgbOqZDfC9lhtOnWiKYDjkD
Unseal Key 4: OvqHrirT/oJCVybMVzNdYcZ1CZb0HbmLcc8d9o1q5l8E
Unseal Key 5: hYXVqBVaveYuB1TAO75Gx7mpCs7DkO0Qqne7Y78t24sF
Initial Root Token: 0d46433c-f82b-6237-9d43-4ab22a73b724
```

## License

BSD-3-Clause
