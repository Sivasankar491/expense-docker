FROM mysql:9.3.0
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1
RUN groupadd expense && \
    useradd -g expense expense && \
    chown -R expense:expense /var/lib/mysql /var/run/mysqld /docker-entrypoint-initdb.d
COPY scripts/*.sql /docker-entrypoint-initdb.d
USER expense
