FROM node:11

WORKDIR /home/

COPY . .

WORKDIR /home/api

RUN npm i nodemon -g && npm i babel-cli -g && npm i && npm run seeds

EXPOSE 3333

CMD [ "npm", "run", "dev" ]

