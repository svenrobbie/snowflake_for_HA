ARG BUILD_FROM=ghcr.io/home-assistant/amd64-base-debian:bookworm
FROM ${BUILD_FROM}

# Copy root filesystem
COPY rootfs /

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Download Snowflake proxy
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    snowflake-proxy=2.3.1-1+b1

RUN rm -rf \
    /tmp/* \
    /var/{cache,log}/* \
    /var/lib/apt/lists/*

# Labels
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION}
