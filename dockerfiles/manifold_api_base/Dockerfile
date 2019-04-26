FROM ruby:2.3.5

ARG MANIFOLD_VERSION

RUN echo "deb [check-valid-until=no] http://cdn-fastly.deb.debian.org/debian jessie main" > /etc/apt/sources.list.d/jessie.list
RUN echo "deb [check-valid-until=no] http://archive.debian.org/debian jessie-backports main" > /etc/apt/sources.list.d/jessie-backports.list
RUN sed -i '/deb http:\/\/deb.debian.org\/debian jessie-updates main/d' /etc/apt/sources.list
RUN apt-get -o Acquire::Check-Valid-Until=false update

RUN apt-get install -y libicu-dev postgresql-client

WORKDIR /opt
RUN wget https://github.com/ManifoldScholar/manifold/archive/v$MANIFOLD_VERSION.tar.gz
RUN tar -xvf v$MANIFOLD_VERSION.tar.gz

WORKDIR /opt/manifold-$MANIFOLD_VERSION

ENV RAILS_LOG_TO_STDOUT=1 RAILS_SERVE_STATIC_FILES=1 RAILS_SERVER_SOCKET_DIR=/manifold_sockets RAILS_SERVER_SOCKET_PATH=/manifold_sockets/manifold-api

RUN gem update --system && gem install bundler

RUN bundle install

RUN bundle install --gemfile=api/Gemfile

RUN mkdir -p /manifold_data/api

RUN ln -s /opt/manifold-$MANIFOLD_VERSION/api/public /manifold_data/api/public

VOLUME ["/manifold_sockets","/manifold_data"]


