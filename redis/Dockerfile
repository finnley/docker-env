ARG REDIS_VERSION
FROM redis:${REDIS_VERSION}-alpine

LABEL maintainer="Finnley <43@43.com>"

#RUN mkdir -p /usr/local/etc/redis
#COPY redis.conf /usr/local/etc/redis/redis.conf

#CMD [ "redis-server", "/usr/local/etc/redis/redis.conf" ]
CMD [ "redis-server"]

EXPOSE 6379