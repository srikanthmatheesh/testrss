FROM nginx:alpine

ADD nginx/default.conf /etc/nginx/conf.d

RUN apk add git

RUN git clone https://git.tt-rss.org/fox/tt-rss.git /app

RUN rm -rf .git

WORKDIR /app

RUN chmod -R 0777 ./cache ./feed-icons ./lock

RUN adduser -D --shell /bin/sh tt-rss
RUN echo "secret_new_remote_user_password" | chpasswd

USER ttrss