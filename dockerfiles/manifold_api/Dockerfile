FROM ruby:2.3.5

ARG MANIFOLD_VERSION

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

WORKDIR /opt
RUN wget https://github.com/ManifoldScholar/manifold/archive/v$MANIFOLD_VERSION.tar.gz
RUN tar -xvf v$MANIFOLD_VERSION.tar.gz

WORKDIR /opt/manifold-$MANIFOLD_VERSION

ENV RAILS_LOG_TO_STDOUT=1 RAILS_SERVE_STATIC_FILES=1 RAILS_SERVER_SOCKET_DIR=/manifold_sockets RAILS_SERVER_SOCKET_PATH=/manifold_sockets/manifold-api

RUN gem update --system && gem install bundler

RUN bundle install

RUN bundle install --gemfile=api/Gemfile

RUN mkdir -p /manifold_data/api/public

RUN cp -r api/public/* /manifold_data/api/public/

VOLUME ["/manifold_sockets","/manifold_data"]
