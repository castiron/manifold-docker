# Manifold Docker

## Using the helper script

```
Usage: ./manifold-docker

Commands:

    build
    compose
    stack

```

## Getting started

Build the images

`./manifold-docker build`

Run the containers 

`./manifold-docker compose up`

Test it out in your browser: 
http://docker.manifold.lvh:4000/api/v1/projects

Take it down

`./manifold-docker compose down`

## Enter the swarm

Alternatively, you can run this through Docker swarm

`./manifold-docker stack up`


Test it out in your browser: 
http://docker.manifold.lvh:4000/api/v1/projects

View the visualizer:
http://localhost:8084

Take it down

`./manifold-docker stack down`


## Next steps

This is under active development. More details coming soon.