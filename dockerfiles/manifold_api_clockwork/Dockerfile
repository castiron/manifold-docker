ARG MANIFOLD_VERSION

FROM manifoldscholar/manifold_api_base:$MANIFOLD_VERSION

ARG MANIFOLD_VERSION

COPY dockerfiles/manifold_api_clockwork/scripts/start-and-run /opt/manifold-$MANIFOLD_VERSION/api/start-and-run

WORKDIR /opt/manifold-$MANIFOLD_VERSION/api

#CMD ["bin/clockwork clock.rb"]
