FROM node:16-alpine

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY app/package.json .
COPY app/package-lock.json .
RUN npm install

COPY app .
RUN npm run build

EXPOSE 3000
CMD ["npm", "run", "start"]
