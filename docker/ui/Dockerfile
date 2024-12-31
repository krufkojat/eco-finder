FROM node:20

WORKDIR /app

COPY package.json package-lock.json ./
RUN yarn install

COPY . .

RUN yarn build

CMD ["npm", "start"]
