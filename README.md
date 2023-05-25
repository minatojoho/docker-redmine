# docker-redmine

Redmine environment sample for macOS Docker Desktop.

# Getting started

## Initial setup

Install Docker Desktop on Mac: https://docs.docker.com/desktop/install/mac-install/

```
$ cd docker-redmine
$ docker-compose build
```

## Run

```
$ cd docker-redmine
$ docker-compose up -d
$ open http://localhost:3000/
```

## Shell

```
$ cd docker-redmine
$ docker-compose up -d
$ docker-compose exec redmine bash
> # cd /usr/src/redmine/
```

# Examples

## Install node.js to redmine container

```
$ cd docker-redmine
$ docker-compose up -d
$ docker-compose exec redmine bash
> # cd; curl https://deb.nodesource.com/setup_18.x | bash
> # curl https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
> # echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
> # apt-get update && apt-get install -y build-essential nodejs yarn
> # cd /usr/src/redmine/plugins/awesome_plugin
> # yarn install
> # yarn build
```

## Restart rails in redmine container

```
$ cd docker-redmine
$ docker-compose up -d
$ docker-compose exec redmine bash
> # pumactl -P /usr/src/redmine/tmp/pids/server.pid restart
```

