FROM node:12
WORKDIR /usr/src/app
COPY package*.json main.js ./
RUN yarn install
EXPOSE 3000 3001
CMD [ "node", "main.js"]
