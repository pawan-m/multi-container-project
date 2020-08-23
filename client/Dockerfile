From node:alpine as builder 

WORKDIR '/apps'

COPY ./package.json ./
RUN npm install
copy . . 
RUN npm run build 

from nginx 
expose 3000
 
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html