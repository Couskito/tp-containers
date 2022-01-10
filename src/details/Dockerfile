# Compléter ici

FROM docker.io/ruby:2.7.1

ARG SERVICE_VERSION "v1"
ARG ENABLE_EXTERNAL_BOOK_SERVICE "false"

WORKDIR /opt/microservices
COPY ./details.rb ./details.rb


EXPOSE 9080

CMD ["ruby", "details.rb", "9080"]