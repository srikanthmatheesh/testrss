FROM nginx:alpine
ADD nginx/default.conf /etc/nginx/conf.d

# COPY ./app/ /app
RUN git clone git@git.tt-rss.org/fox/tt-rss.git /app

WORKDIR /app

RUN chmod -R 0777 ./cache ./feed-icons ./lock