# FROM node:22
# RUN mkdir /opt/server
# ADD https://expense-builds.s3.us-east-1.amazonaws.com/expense-backend-v2.zip /tmp/backend.zip
# WORKDIR /opt/server
# RUN unzip /tmp/backend.zip
# ENV DB_HOST="mysql"
# RUN npm install
# EXPOSE 8080
# CMD ["node", "index.js"]


FROM node:20
EXPOSE 8080
ENV DB_HOST="mysql"
RUN mkdir /opt/server
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install
CMD ["node", "index.js"]