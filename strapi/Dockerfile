ARG BASE_VERSION
FROM strapi/base:4.0.0

ARG STRAPI_VERSION
RUN yarn global add @strapi/strapi@4.0.0

RUN mkdir /srv/app && chown 1000:1000 -R /srv/app

WORKDIR /srv/app

VOLUME /srv/app

COPY docker-entrypoint.sh /usr/local/bin/
RUN chmod 777 /usr/local/bin/docker-entrypoint.sh 
ENTRYPOINT ["docker-entrypoint.sh"]

CMD ["strapi", "develop"]
