FROM node:alpine AS builder

WORKDIR "/client"

COPY ./package.json ./
COPY ./package-lock.json ./

RUN npm install
RUN npm audit fix

COPY . .

RUN npm run build

FROM nginx

EXPOSE 3000

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

COPY --from=builder /client/build /usr/share/nginx/html