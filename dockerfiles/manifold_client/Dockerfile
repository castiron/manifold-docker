FROM node:8.11.2

ARG MANIFOLD_VERSION

COPY manifold /opt/manifold
WORKDIR /opt/manifold/client
RUN yarn install && yarn build:prod
VOLUME ["/manifold_sockets","/manifold_data"]
