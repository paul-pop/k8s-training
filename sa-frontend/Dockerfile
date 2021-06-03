# Stage 1 - Install dependencies
FROM node:14 AS builder

COPY package.json .
COPY yarn.lock .

RUN yarn install

# Stage 2 - Compile bundle and set app version
COPY public ./public
COPY src ./src

RUN yarn build

# Stage 3 - Create production container
FROM nginx:1.21

WORKDIR /usr/share/nginx/html

COPY --from=builder build ./

EXPOSE 80

CMD ["/bin/bash", "-c", "nginx -g \"daemon off;\""]
