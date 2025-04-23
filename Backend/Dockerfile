FROM node:22
RUN useradd expense && \
    mkdir /app
ADD https://expense-builds.s3.us-east-1.amazonaws.com/expense-backend-v2.zip /app
WORKDIR /app
ENV DB_HOST="mysql"
RUN npm install
CMD ["node", "index.js"]