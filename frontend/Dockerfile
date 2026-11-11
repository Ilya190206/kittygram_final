FROM node:18
ARG PUBLIC_URL=""
ENV PUBLIC_URL=${PUBLIC_URL}
WORKDIR /app

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npm ci

COPY . .
RUN npm run build
RUN npm install --global http-server

CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]
