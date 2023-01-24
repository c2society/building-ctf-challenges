FROM node:stretch-slim

# hadolint ignore=DL3027
RUN apt update && apt install unzip && \
    echo 'example.the-petting-zoo.com' >> /etc/hostname && \
    mkdir -p /srv

COPY app /srv/
WORKDIR /srv/app

RUN npm install --no-optional

EXPOSE 8080

CMD [ "npm", "start" ]
