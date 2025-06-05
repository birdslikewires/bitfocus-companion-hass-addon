ARG BUILD_ARCH=aarch64

# Select the correct image based on the architecture linux/arm64=aarch64_image linux/amd64=amd64_image
FROM ghcr.io/bitfocus/companion/companion:stable-3.5@sha256:68af2d2ae4fe391f1986ebdbf942d7c0c6791e8a66e4788c76f972f4f62ec6c4 AS aarch64_image
FROM ghcr.io/bitfocus/companion/companion:stable-3.5@sha256:1c2fb739cf177a3f8d7c2724c1bc30a08b7e7b10686b15a206563543bdfa82f5 AS amd64_image


# The actual image used
FROM ${BUILD_ARCH}_image

USER root

# Copy the startup script
COPY run.sh /run_companion.sh
RUN chmod +x /run_companion.sh

# Change the entry point
ENTRYPOINT ["/run_companion.sh"]
