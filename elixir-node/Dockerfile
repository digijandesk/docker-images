ARG ELIXIR_VERSION

FROM elixir:${ELIXIR_VERSION}

ARG NODE_VERSION

RUN set -xe \
# get apt ready to install node - see https://github.com/nodesource/distributions#deb
&& curl -fsSL https://deb.nodesource.com/setup_${NODE_VERSION}.x | bash - \
&& apt-get update \
&& apt-get install -y nodejs \ 
# set up mix and rebar
&& mix local.hex --force \
&& mix local.rebar --force 