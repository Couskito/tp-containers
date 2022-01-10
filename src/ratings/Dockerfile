# Compléter ici

FROM docker.io/node:12.18.1
WORKDIR /opt/microservices

COPY ./package.json ./

RUN ["npm", "install"]

COPY ./ratings.js ./

RUN apt-get update && apt-get install curl --no-install-recommends -y && rm -rf /var/lib/apt/lists/*

ARG SERVICE_VERSION="v1"
ENV SERVICE_VERSION=$SERVICE_VERSION

EXPOSE 9080
CMD ["node", "ratings.js", "9080"]