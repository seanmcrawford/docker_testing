FROM node:alpine as builder
WORKDIR '/home/app'
COPY package.json .
RUN npm install
COPY package*.json ./
RUN npm run build

FROM nginx:alpine
EXPOSE 80
COPY --from=builder /home/app/build /usr/share/nginx/html