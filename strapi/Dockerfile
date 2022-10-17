ARG NODE_VERSION
FROM node:18.11-alpine AS base
EXPOSE 1337

ARG BASE_VERSION
#FROM strapi/base:${BASE_VERSION}
FROM base

ARG STRAPI_VERSION
RUN yarn global add @strapi/strapi@${STRAPI_VERSION}

RUN mkdir /srv/app && chown 1000:1000 -R /srv/app

WORKDIR /srv/app

VOLUME /srv/app

COPY docker-entrypoint.sh /usr/local/bin/
RUN chmod 777 /usr/local/bin/docker-entrypoint.sh 
ENTRYPOINT ["docker-entrypoint.sh"]

CMD ["strapi", "develop"]
