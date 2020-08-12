FROM node:alpine as mybuilder
WORKDIR '/app'
COPY ./package.json .
RUN npm install
COPY . .
RUN npm run build


FROM nginx
EXPOSE 80
COPY --from=mybuilder /app/build /usr/share/nginx/html
