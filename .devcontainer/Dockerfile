# Elixir + Phoenix

FROM elixir:1.13

ENV DEBIAN_FRONTEND=noninteractive

# Install debian packages
RUN apt-get update
RUN apt-get install --yes build-essential inotify-tools postgresql-client wget

# Install Phoenix packages
RUN mix local.hex --force
RUN mix local.rebar --force
RUN mix archive.install hex phx_new --force

# Install node
RUN curl -sL https://deb.nodesource.com/setup_16.x -o nodesource_setup.sh
RUN bash nodesource_setup.sh
RUN apt-get install -y nodejs

ENV DEBIAN_FRONTEND=dialog

WORKDIR /app
EXPOSE 4000
