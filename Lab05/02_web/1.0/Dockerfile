FROM nginx:stable

ENV TZ=America/Lima
#ADD data/nginx.conf /etc/nginx/nginx.conf
ADD ./dist /usr/share/nginx/html

ENTRYPOINT ["nginx", "-g", "daemon off;"]
#CMD ["nginx"]