FROM nginx:1.15.2

COPY dockerfiles/manifold_proxy/config/default.conf /etc/nginx/conf.d/default.conf

COPY dockerfiles/manifold_proxy/config/docker_localhost_cert.pem /etc/nginx/ssl/docker_localhost_cert.pem

COPY dockerfiles/manifold_proxy/config/docker_localhost_key.pem /etc/nginx/ssl/docker_localhost_key.pem

VOLUME ["/manifold_sockets","/manifold_data"]

EXPOSE 80 443

CMD [ "nginx", "-g", "daemon off;" ]
