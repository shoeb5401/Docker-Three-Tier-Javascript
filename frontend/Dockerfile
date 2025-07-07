FROM node:20.19.3-bullseye

WORKDIR /frontend

COPY . /frontend

RUN npm install 

ENV NODE_OPTIONS=--openssl-legacy-provider

CMD ["npm" , "start" , "--" ,"--host"]
