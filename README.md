# Manifold Docker

## Requirements

### General

* 4GB RAM
* 2 CPU cores


### Docker
* Install Docker for your platform: https://docs.docker.com/install/
    * _Recommended that you install the current version but minimum version >= 17.03_
 
* Install docker-compose for your platform: https://docs.docker.com/compose/install/
    * _Note: docker-compose might be installed already with docker depending on your platform._

* Install docker-machine for your platform: https://docs.docker.com/machine/install-machine/
    * _Note: docker-machine might be installed already with docker depending on your platform._

### OS X

* Install VirtualBox: https://www.virtualbox.org/wiki/Downloads
     * _This is a temporary requirement and will be removed once this issue with Docker for Mac is resolved:
https://github.com/docker/for-mac/issues/1835_

## Setup

### Option 1
Clone this repo: 

`git clone git@github.com:ManifoldScholar/manifold-docker.git`

The master branch will always track the latest Manifold release: https://github.com/ManifoldScholar/manifold/releases

Alternatively, you can then checkout a specific tag that corresponds to a Manifold release.

### Option 2

Download a specific release:
https://github.com/ManifoldScholar/manifold-docker/releases


## Getting started

### Run the containers

`./manifold-docker compose up 1.0.1`

After the script completes, some basic usage information will be displayed.

An optional domain parameter can be passed to allow access using a domain.

`./manifold-docker compose up 1.0.1 example.domain.com`

Take it down

`./manifold-docker compose down`

### Enter the swarm

Alternatively, you can run this through Docker swarm

`./manifold-docker stack up 1.0.1`

After the script completes, some basic usage information will be displayed.

An optional domain parameter can be passed to allow access using a domain.

`./manifold-docker stack up 1.0.1 example.domain.com`

Take it down

`./manifold-docker stack down`
