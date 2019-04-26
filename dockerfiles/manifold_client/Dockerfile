FROM node:8.11.2

ARG MANIFOLD_VERSION

# Install Ruby
#RUN mkdir /tmp/ruby
#RUN cd /tmp/ruby && curl --silent https://cache.ruby-lang.org/pub/ruby/2.3/ruby-2.3.5.tar.gz | tar xz
#RUN cd /tmp/ruby/ruby-2.3.5 && ./configure --disable-install-rdoc && make install

WORKDIR /opt
RUN wget https://github.com/ManifoldScholar/manifold/archive/v$MANIFOLD_VERSION.tar.gz
RUN tar -xvf v$MANIFOLD_VERSION.tar.gz

WORKDIR /opt/manifold-$MANIFOLD_VERSION

#RUN gem update --system

#RUN bundle install

WORKDIR /opt/manifold-$MANIFOLD_VERSION/client

RUN yarn install && yarn build:prod

VOLUME ["/manifold_sockets","/manifold_data"]
