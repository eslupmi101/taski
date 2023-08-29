FROM node:18

WORKDIR /app

COPY package.json package.json

COPY package-lock.json package-lock.json

RUN npm ci

COPY . .

RUN npm run build

RUN npm install --global http-server

RUN mkdir /frontend_static/

RUN cp -r /app/build/. /frontend_static/.

CMD ["npx", "-y", "http-server", "-p", "8001", "/app/build"]
