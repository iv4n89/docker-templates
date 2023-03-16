# syntax=docker/dockerfile:1.4
FROM --platform=$BUILDPLATFORM node:14.4.0-alpine AS development

RUN mkdir /project
WORKDIR /project

COPY . .

RUN npm i -g @vue/cli
RUN npm i
ENV HOST=0.0.0.0
CMD ["npm", "run", "dev"]

FROM development as dev-envs
RUN <<EOF
apk update
apk add git
EOF

RUN <<EOF
addgroup -S docker
adduser -S --shell /bin/bash --ingroup docker vscode
EOF
# install Docker tools (cli, buildx, compose)
COPY --from=gloursdocker/docker / /
CMD ["npm", "run", "dev"]