FROM node:22-alpine3.22

RUN apk update && apk upgrade --no-cache

WORKDIR /app

COPY package.json ./

RUN npm install --omit=dev \
    && npm cache clean --force \
    && rm -rf /root/.npm \
    && rm -rf /usr/local/lib/node_modules/npm \
    && rm -f /usr/local/bin/npm /usr/local/bin/npx

COPY app.js ./

EXPOSE 3000

CMD ["node", "app.js"]
