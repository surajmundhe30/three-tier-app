FROM node:14
WORKDIR /usr/src/app
COPY package.json .
RUN npm install
RUN npm install cors
COPY . .
CMD ["node", "app.js"]
