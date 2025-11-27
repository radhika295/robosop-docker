FROM node:20.19.6-alpine3.21 AS build
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install

FROM node:20.19.6-alpine3.21
#create a group and user
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
WORKDIR /opt/server
#whatever is running under user are runing as roboshop user
USER roboshop
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