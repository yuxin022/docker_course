FROM node:latest

#every line is a new image therefore one huge line
ENV DB_HOST=mydb DB_USER=root DB_PASSWORD=changeit DB_PORT=3306 APP_PORT=3000 APP_DIR=/app

RUN mkdir ${APP_DIR}
WORKDIR ${APP_DIR}

#install libs
ADD package.json .
ADD package-lock.json .
RUN npm install

# ADD statements below
ADD config config
ADD public public
ADD views views

ADD main.js .

#Expose ports
EXPOSE ${APP_PORT}

ENTRYPOINT ["node", "main.js"]
CMD ["$APP_PORT"]