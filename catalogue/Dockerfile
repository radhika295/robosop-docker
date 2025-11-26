FROM node:20
WORKDIR /opt/server
COPY pacakge.json .
COPY *.js .
RUN npm install
ENV MONGO="true" \ 
    MONGO_URL="mongodb://sweet_noyce:27017/catalogue"
CMD ["node" , "server.js"]