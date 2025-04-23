FROM node:22
RUN mkdir /opt/server
WORKDIR /opt/server
ADD https://expense-builds.s3.us-east-1.amazonaws.com/expense-backend-v2.zip .
ENV DB_HOST="mysql"
RUN npm install
CMD ["node", "index.js"]