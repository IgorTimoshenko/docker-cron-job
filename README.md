## cron-job Dockerfile


This repository contains **Dockerfile** of cron-job for [Docker](https://www.docker.com/)'s [automated build](https://registry.hub.docker.com/u/igortimoshenko/docker-cron-job/) published to the public [Docker Hub Registry](https://registry.hub.docker.com/).


### Base Docker Image

* [dockerfile/ubuntu](http://dockerfile.github.io/#/ubuntu)


### Installation

1. Install [Docker](https://www.docker.com/).

2. Download [automated build](https://registry.hub.docker.com/u/igortimoshenko/docker-cron-job/) from public [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull igortimoshenko/docker-cron-job`

   (alternatively, you can build an image from Dockerfile: `docker build -t="igortimoshenko/docker-cron-job" github.com/igortimoshenko/docker-cron-job`)


### Usage

Start container specifying the executable script for cron:

    docker run -d \
    -v `<script-dir>`/cron.sh:/root/cron.sh \
    -e CRON_JOB='* * * * * ~/cron.sh' \
    igortimoshenko/docker-cron-job

> Note that if you need environment variables within your cron script then add
> the following line `source /root/.env-vars` to your script
