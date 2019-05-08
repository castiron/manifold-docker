<div align="center">
    <img src="https://storage.googleapis.com/manifold-assets/readme-art.gif" width="400" /><br />
    <h1>
        Manifold Scholarship
    </h1>
</div>

<p align="center">
    Manifold is an intuitive, collaborative platform for scholarly publishing. With iterative texts, powerful annotation tools, rich media support, and robust community dialogue, Manifold transforms scholarly publications into living digital works.
</p>

<p align="center">
    Learn more at <a href="https://manifoldapp.org">manifoldapp.org</a>.<br />
    See it in action at <a href="https://manifold.umn.edu">manifold.umn.edu</a>.<br />
    Join our <a href="https://manifold-slackin.herokuapp.com/">Slack Channel</a><br />
    <a href="https://github.com/ManifoldScholar/manifold/issues/new?template=bugs.md">Report a bug</a>.<br />
    <a href="https://github.com/ManifoldScholar/manifold/issues/new?template=features.md">Request a feature</a>.
</p>

## Manifold Docker

## Requirements

### General

* Minimum
    * 4GB RAM
    * 2 CPU cores
* Recommended
    * 6GB RAM
    * 4 CPU cores

### OS X

* Install VirtualBox: https://www.virtualbox.org/wiki/Downloads
     * _This is a temporary requirement and will be removed once this issue with Docker for Mac is resolved:
https://github.com/docker/for-mac/issues/1835_

### Linux

Tested on Ubuntu 16.04 LTS and 18.04 LTS. No additional requirements outside of installing Docker (see below).

### Windows

* Virtualization must be enabled in BIOS
* Hyper-V will automatically be enabled which will prevent VirtualBox from working
    * If this is a problem, then recommendation is to use Docker Toolbox instead
* *Requires Windows 10 Pro, Enterprise, or Education*
* git-bash should be installed (https://git-scm.com/download/win)

git-bash settings selected during testing:
* Use Git from Git Bash only (required change)
* Use the OpenSSL library (default)
* Checkout Windows-style, commit Unix-style line endings (default)
* Use MinTTY (the default terminal of MSYS2) (default)
* Enable file system caching (default)
* Enable Git Credential Manager (default)
* Enable symbolic links (required change)

### Docker
* Install Docker for your platform: https://docs.docker.com/install/
    * _Recommended that you install the current version but minimum version >= 17.03_
    * _For Windows minimum version >= 18.06.0-ce-win70 (build: 19075)_

* Install docker-compose for your platform: https://docs.docker.com/compose/install/
    * _Note: docker-compose might be installed already with docker depending on your platform._

## Caveats

### Windows

To work around path conversion issues in git-bash you need to run the following prior to using the `./manifold-docker`
script.

`export COMPOSE_CONVERT_WINDOWS_PATHS=1 MSYS_NO_PATHCONV=1;`

To work around communication between containers, host.docker.internal is used. As a result, you must pass the `DOMAIN`
parameter when using `./manifold-docker`. If you are not using a domain, you can simply pass `127.0.0.1`. Example using
compose:

`./manifold-docker compose up 1.0.1 127.0.0.1`  


## Setup

### Option 1
Clone this repo:

`git clone https://github.com/ManifoldScholar/manifold-docker.git`

The master branch will always track the latest Manifold release: https://github.com/ManifoldScholar/manifold/releases

Alternatively, you can then checkout a specific tag that corresponds to a Manifold release.

### Option 2

Download a specific release:
https://github.com/ManifoldScholar/manifold-docker/releases


## Getting started

Build the base API Image:
`./manifold-docker build 3.0.0 api_base`

Build the API services:
`./manifold-docker build 3.0.0 api_services`

Build the Client:
`./manifold-docker build 3.0.0`

Run it:
`MANIFOLD_TAG=3.0.0 docker-compose -f compose/docker-compose.yml up -d`

View it:
https://manifold.lvh:4001/

Stop it:
`docker-compose -f compose/docker-compose.yml down -v`
