FROM mysql:8.0
# not a human, only for system
RUN adduser -r expense
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1 \
    MYSQL_USER=expense \
    MYSQL_PASSWORD=ExpenseApp@1 \
    MYSQL_DATABASE=transactions
#giving perm to user expense to the directories
RUN chown -R expense:expense /var/lib/mysql /var/run/mysqld
#Copying the .sql files and placing at docker entry point where the entrypoint is executed when container is started
COPY scripts/*.sql /docker-entrypoint-initdb.d/ 