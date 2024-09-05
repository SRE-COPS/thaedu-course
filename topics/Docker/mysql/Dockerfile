# Use the official MySQL image
FROM mysql:latest

# Set environment variables
ENV MYSQL_ROOT_PASSWORD=mysqldb

# When the container starts, this SQL will be executed.
# Add additional SQL scripts or commands here if needed.
COPY ./init.sql /docker-entrypoint-initdb.d/

# Expose the default MySQL port
EXPOSE 3306

# Set up the volume where the database data will be stored
VOLUME /var/lib/mysql

# The default command to run when starting the container
CMD ["mysqld"]
