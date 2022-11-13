FROM docker.io/alpine:3.16.2
#FROM arm64v8/alpine:3.16.2

LABEL AUTHOR="Michael Pilosov <consistentbayes@gmail.com>"

# Install pygments (for syntax highlighting) and bash
RUN apk update && \
    apk --no-cache add \
    py-pygments \
    bash \
    git \
    libc6-compat \
    g++ \
    && rm -rf /var/cache/apk/*

# HUGO
ARG VER
ARG VAR
ARG ARCH
ENV HUGO_VERSION ${VER}
ENV HUGO_BINARY hugo_${VAR}${HUGO_VERSION}_linux-${ARCH}

# Download and Install hugo
RUN mkdir /usr/local/hugo
ADD https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/${HUGO_BINARY}.tar.gz /usr/local/hugo/
RUN tar xzf /usr/local/hugo/${HUGO_BINARY}.tar.gz -C /usr/local/hugo/ \
    && ln -s /usr/local/hugo/hugo /usr/local/bin/hugo \
    && rm /usr/local/hugo/${HUGO_BINARY}.tar.gz

EXPOSE 1313
CMD hugo version

ARG APP_USER="hugo"
ARG APP_UID="1000"

# Create a group and user
RUN addgroup -S appgroup && \
    adduser --disabled-password \
            -S $APP_USER \
            -G appgroup \
            -s /bin/bash \
            -u $APP_UID \
            -g "Default user" -H

USER ${APP_USER}

WORKDIR /tmp
