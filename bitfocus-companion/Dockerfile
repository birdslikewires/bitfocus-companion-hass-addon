ARG BUILD_ARCH=aarch64

# Select the correct image based on the architecture linux/arm64=aarch64_image linux/amd64=amd64_image
FROM ghcr.io/bitfocus/companion/companion:4.0.0-8052-stable-68859c8a39@sha256:ca9a84e2ffd1adbf5202a213cee58506cf3bbba63c0d556bcf8637f48680da46 AS aarch64_image
FROM ghcr.io/bitfocus/companion/companion:4.0.0-8052-stable-68859c8a39@sha256:8db5b864271acbebf63a1e091ea52f4820492b42f82094e0121b44a479d1b64d AS amd64_image


# The actual image used
FROM ${BUILD_ARCH}_image

USER root

# Copy the startup script
COPY run.sh /run_companion.sh
RUN chmod +x /run_companion.sh

# Change the entry point
ENTRYPOINT ["/run_companion.sh"]
