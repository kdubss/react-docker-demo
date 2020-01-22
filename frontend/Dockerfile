# 1st block - building the App
FROM node:alpine as builder

WORKDIR /app

COPY package.json .
RUN npm install

COPY . .
RUN npm run build

# 2nd block - Serving the production app
FROM nginx

COPY --from=builder /app/build /usr/share/nginx/html

