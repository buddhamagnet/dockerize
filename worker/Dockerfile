FROM node:alpine

WORKDIR "/worker"

COPY ./package.json ./
COPY ./package-lock.json ./

RUN npm install

COPY . .

CMD ["npm", "run", "start"]