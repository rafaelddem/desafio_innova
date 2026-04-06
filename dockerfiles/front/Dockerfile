FROM node:20-alpine

ENV NODE_ENV=development
ENV VUE_APP_API_URL=http://127.0.0.1:8000/api/

RUN apk add --no-cache git

RUN git config --global user.name "Rafael" \
    && git config --global user.email "rafaelddem@gmail.com" 

RUN git clone -b main https://github.com/rafaelddem/desafio_innova_front.git /var/www/html \
    && git config --global --add safe.directory /var/www/html

WORKDIR /var/www/html

RUN npm install -g @vue/cli

RUN npm install --legacy-peer-deps

EXPOSE 8080

CMD ["npm", "run", "serve"]
