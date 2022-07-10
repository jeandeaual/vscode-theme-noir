# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.163.0/containers/typescript-node/.devcontainer/base.Dockerfile

# [Choice] Node.js version: 18, 16, 14, 12, 10
ARG VARIANT="18"

FROM mikefarah/yq:4 AS yq

FROM mcr.microsoft.com/vscode/devcontainers/typescript-node:0-${VARIANT}

# Install additional global node packages
RUN su node -c "npm install -g yo generator-code"

# Install the yq command (to convert from JSON to YAML)
COPY --from=yq /usr/bin/yq /usr/bin/yq
