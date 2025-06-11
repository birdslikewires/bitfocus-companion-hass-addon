ARG BUILD_ARCH=arm64

# Select the correct image based on the architecture
FROM ghcr.io/bitfocus/companion/companion:4.0.1-8061-stable-b1c1c1f4dd@sha256:85a43a935fa91cfe3aaac02b68f2106b421280f0df8068a13254243a769c5dd2 AS amd64_image
FROM ghcr.io/bitfocus/companion/companion:4.0.1-8061-stable-b1c1c1f4dd@sha256:c39fd3d22a7faef37de9b39f61e7e46e8b59e3f2a5ef85d697d2b3cfd473c4cb AS arm64_image

# The actual image used
FROM ${BUILD_ARCH}_image

USER root

# Copy the startup script
COPY run.sh /run_companion.sh
RUN chmod +x /run_companion.sh

# Change the entry point
ENTRYPOINT ["/run_companion.sh"]
