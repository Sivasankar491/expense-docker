# FROM node:22
# RUN mkdir /opt/server
# ADD https://expense-builds.s3.us-east-1.amazonaws.com/expense-backend-v2.zip /tmp/backend.zip
# WORKDIR /opt/server
# RUN unzip /tmp/backend.zip
# ENV DB_HOST="mysql"
# RUN npm install
# EXPOSE 8080
# CMD ["node", "index.js"]


FROM node:20 AS builder
ADD https://expense-builds.s3.us-east-1.amazonaws.com/expense-backend-v2.zip /tmp/backend.zip
WORKDIR /opt/server
RUN unzip /tmp/backend.zip
RUN npm install


FROM node:20.18.0-alpine3.20
EXPOSE 8080
ENV DB_HOST="mysql"
RUN addgroup -S expense && adduser -S expense -G expense && \
    mkdir /opt/server && \
    chown -R expense:expense /opt/server
WORKDIR /opt/server
COPY --from=builder /opt/server /opt/server
USER expense
CMD ["node", "index.js"]