FROM mysql:8.0
# not a human user, only for system user
RUN adduser -r expense
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1 \
    MYSQL_USER=expense \
    MYSQL_PASSWORD=ExpenseApp@1 \
    MYSQL_DATABASE=transactions
#giving access to the user expense to the mysql directories
RUN chown -R expense:expense /var/lib/mysql /var/run/mysqld
#copying the .sql files to the docker entrypoint
COPY scripts/*.sql /docker-entrypoint-initdb.d/