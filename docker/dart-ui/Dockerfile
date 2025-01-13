FROM debian:latest

RUN apt-get update
RUN apt-get install -y curl git unzip

ARG FLUTTER_SDK=/usr/local/flutter
ARG APP=/var/www/ui

RUN git clone https://github.com/flutter/flutter.git $FLUTTER_SDK
RUN cd $FLUTTER_SDK && git fetch

ENV PATH="$FLUTTER_SDK/bin:$FLUTTER_SDK/bin/cache/dart-sdk/bin:${PATH}"

RUN flutter doctor -v

WORKDIR $APP

EXPOSE 9000