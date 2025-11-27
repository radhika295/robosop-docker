FROM node:20.19.6-alpine3.21 as build
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install

FROM node:20.19.6-alpine3.21
WORKDIR /opt/server
COPY --from=build /opt/server //opt/server
ENV MONGO="true" \ 
    MONGO_URL="mongodb://mongodb:27017/catalogue"
CMD ["node" , "server.js"]





# FROM node:20
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# ENV MONGO="true" \ 
#     MONGO_URL="mongodb://mongodb:27017/catalogue"
# CMD ["node" , "server.js"]