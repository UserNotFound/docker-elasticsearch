# ![](https://gravatar.com/avatar/11d3bc4c3163e3d238d558d5c9d98efe?s=64) aptible/elasticsearch
[![Docker Repository on Quay.io](https://quay.io/repository/aptible/elasticsearch/status)](https://quay.io/repository/aptible/elasticsearch)
[![Build Status](https://travis-ci.org/aptible/docker-elasticsearch.svg?branch=master)](https://travis-ci.org/aptible/docker-elasticsearch)

[![](http://dockeri.co/image/aptible/elasticsearch)](https://registry.hub.docker.com/u/aptible/elasticsearch/)

Elasticsearch on Docker.

## Installation and Usage

    docker pull quay.io/aptible/elasticsearch

This is an image conforming to the [Aptible database specification](https://support.aptible.com/topics/paas/deploy-custom-database/). To run a server for development purposes, execute

    docker create --name data quay.io/aptible/elasticsearch
    docker run --volumes-from data -e USERNAME=aptible -e PASSPHRASE=password -e DB=db quay.io/aptible/elasticsearch --initialize
    docker run --volumes-from data -P quay.io/aptible/elasticsearch

The first command sets up a data container named `data` which will hold the configuration and data for the database. The second command creates an Elasticsearch instance with a username, passphrase and database name of your choice. The third command starts the database server.

## Available Tags

* `latest`: Currently Elasticsearch 7.5
* `7.5`
* `7.4`

## Tests

Tests are run as part of the `Dockerfile` build. To execute them separately within a container, run:

    bats test

## Deployment

To push the Docker image to Quay, run the following command:

    make push

## Continuous Integration

Images are built and pushed to Quay and the Docker Hub on push to master in
Travis.

## Copyright and License

MIT License, see [LICENSE](LICENSE.md) for details.

Copyright (c) 2019 [Aptible](https://www.aptible.com), [Frank Macreery](https://github.com/fancyremarker), and contributors.
