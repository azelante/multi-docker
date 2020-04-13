FROM node:alpine as builder
WORKDIR '/app'
copy ./package.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etx/nginx/conf.d/default.conf
COPY --from=builder /app/build /urs/share/nginx/html

