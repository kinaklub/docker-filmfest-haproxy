# Dockerfile of HAProxy configuration for next.filmfest.by

This repository contains HAProxy with configuration optimized for
[next.filmfest.by](http://next.filmfest.by) that's running inside
docker in swarm mode.

## Overview

We use `Makefile` for automating docker image build process. Image
version is taken from submodule using `git descrbie --tags`.

## Build Requirements

* make
* docker client (available without `sudo`)
* git

## Build Process

Build docker images:

```sh
make
# or
make build
```

Publish docker image:

```sh
make push
```

Publish docker image as `latest`:

```sh
make push-latest
```

Long story shot, in order to release a new version one needs to:

* add git tag with an appropriate version
* build image using `make`
* push image using `make push` (and optionally `make push-latest`)
