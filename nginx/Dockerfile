FROM nginx:alpine
ADD nginx/default.conf /etc/nginx/conf.d

# COPY ./app/ /app

WORKDIR /app

RUN chmod -R 0777 ./cache ./feed-icons ./lock