FROM mysql:latest
ENV MYSQL_ROOT_PASSWORD="shiva"
ENV MYSQL_DATABASE="accounts"
ADD db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql


