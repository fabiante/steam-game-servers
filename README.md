# Steam Game Servers 🎮

A single repository for multiple Dockerfiles related to Steam Servers.

These Dockerfiles should simplify running dedicated servers on you local computer or any Docker environment.

Here is a list of supported servers: [Supported Servers](#supported-servers)

## Prerequisite

- Basic understanding of Docker: You should be at least to locally build and run images, open ports and map volumes.
- Basic linux skills: You should be able to navigate the fs and do some networking stuff. If you are able to do automated backups you would benefit from that so that you can backup your savegames.

## General Usage

There are two ways to use this repository.

The first one uses `docker-compose` files. With this you will not have to manually build the images and run them: [Compose Files](#compose-files)

The second one is to run all steps manually: [Manual Builds](#manual-builds)

## Compose Files

All server dirs should also have a `docker-compose.yml` that helps you get your server running quickly.

Before using a servers compose image, please read the related README.

Starting a server via the compose file is as simple as running:

```sh
docker-compose -f ./servers/ark-survival-evolved/docker-compose.yml up
```

If there isn't a compose file or an existing one does not work, please exuse us. Keeping all of the compose files up to date is not
always possible and takes time. Please submit a PR or create an issue if something is missing or doesn't work.

## Manual Builds

### 1. Build Base Image

All images rely on a base image that contains [SteamCMD](https://developer.valvesoftware.com/wiki/SteamCMD) and other components.

So first you will have to build that image with this command:

```sh
docker build -t steam-cmd:latest ./base
```

### 2. Build Game Server Image

Now you will want to build the image that contains the game server. To do so, read the README files of the server directory for specific steps.

Generally you build the images like:

```sh
docker build -t ark:latest ./servers/ark-survival-evolved
```

## Contributing

Want to run a game server in Docker that isn't yet listed here? We would love to help and integrate your server into this repository.

Simply create an issue or a PR.

## Supported Servers

- [ARK: Survival Evolved](./servers/ark-survival-evolved/README.md)
- [MORDHAU](./server/mordhau/README.md)
