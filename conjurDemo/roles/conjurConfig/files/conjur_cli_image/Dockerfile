FROM cyberark/conjur-cli:5-6.1.0

COPY ./apiInteraction /scripts/

COPY ./policy /policy/

COPY ./tls /tls

RUN apt-get update -y && apt-get install openssl -y

WORKDIR /tls

RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -config tls.conf -extensions v3_ca -keyout nginx.key -out nginx.crt

WORKDIR /scripts