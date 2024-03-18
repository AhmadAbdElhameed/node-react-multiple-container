FROM node:latest

WORKDIR /app

COPY package.json /app/

RUN npm install

COPY . .

EXPOSE 80

ENV MONGODB_USERNAME=ahmad

ENV MONGODB_PASSWORD=secret

CMD [ "npm" ,"start" ]