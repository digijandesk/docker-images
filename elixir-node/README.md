# digijandesk/docker-images/elixir-node

## description

derived from the official elixir:$ELIXIR_VERSION base image, where you supply
ELIXIR_VERSION as shown in the [usage example](#usage-example). Uses apt to
fetch and install the official debian NodeSource Node.js Binary Distribution for
the given major NODE_VERSION.

## rationale

useful for Elixir Phoenix project builds, which need node to build assets such as js, html, and (s)css

## arguments ( --build-arg )

### ELIXIR_VERSION

- Elixir version to build from
- See [Dockerhub](https://hub.docker.com/_/elixir) for official list of supported versions
- note: image must support debian packages and apt. standard elixir images currently support apt / debian.

### NODE_VERSION

- Major Node version (e.g., 14)
- See [Node Source](https://github.com/nodesource/distributions#deb) for official list of supported versions.

## usage example

build the image defined in Dockerfile with docker

```sh
$ NODE_VERSION=12 ELIXIR_VERSION=1.11.3 \ 
docker build . \
 -t digijandesk/elixir-node${NODE_VERSION}:${ELIXIR_VERSION} \
 --build-arg ELIXIR_VERSION=${ELIXIR_VERSION} \
 --build-arg NODE_VERSION=${NODE_VERSION}
```
