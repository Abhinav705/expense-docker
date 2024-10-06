FROM node:20.15.0-alpine3.20
EXPOSE 8080
ENV DB_HOST=mysql
#creating group expense and adding user expense to the group expense
#creating dir opt/server and giving perm to user expense to that dir
RUN addgroup -S expense && adduser -S expense -G expense \
    && mkdir /opt/server \
    && chown expense:expense -R /opt/server
#cd /opt/server
WORKDIR /opt/server
COPY package.json .
COPY *.js /opt/server/
RUN npm install
USER expense
EXPOSE 8081
CMD [ "node","index.js" ]