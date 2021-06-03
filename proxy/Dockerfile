FROM nginxinc/nginx-unprivileged

RUN echo "server { \
              listen 8088 ; \
              location / { \
                  proxy_pass http://backend:8002 ; \
              } \
          }" > /etc/nginx/conf.d/default.conf

EXPOSE 8088
