FROM node:20

WORKDIR /app

RUN npm i -g pnpm

COPY package.json .
COPY pnpm-lock.yaml .

RUN pnpm install

COPY . .

RUN pnpm generate

RUN pnpm build

ENV NODE_ENV=production

ENTRYPOINT [ "node", "dist/server" ]
