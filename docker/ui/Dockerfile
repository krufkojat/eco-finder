FROM node:23-alpine

WORKDIR /app

COPY . .

RUN yarn install

RUN yarn build

CMD ["yarn", "dev"]
