FROM node:24-alpine

WORKDIR /app

COPY package.json yarn.lock ./
RUN yarn install --frozen-lockfile

COPY tsconfig*.json ./
COPY vite.config.ts ./
COPY index.html ./
COPY public ./public
COPY src ./src

RUN yarn build

EXPOSE 3000

CMD ["npx", "serve", "-s", "dist", "-l", "3000"]
