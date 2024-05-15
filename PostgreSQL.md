# Install and Configure Postgre SQL

The Nautilus application development team has shared that they are planning to deploy one newly developed application on Nautilus infra in Stratos DC. The application uses PostgreSQL database, so as a pre-requisite we need to set up PostgreSQL database server as per requirements shared below:



PostgreSQL database server is already installed on the Nautilus database server.

1. Create a database user kodekloud_joy and set its password to BruCStnMT5.


1. Create a database kodekloud_db7 and grant full permissions to user kodekloud_joy on this database.


Note: Please do not try to restart PostgreSQL server service.


# solution

`sudo -u postgres psql`

`CREATE USER kodekloud_joy WITH PASSWORD 'BruCStnMT5';`  

`CREATE DATABASE kodekloud_db7;`  

`GRANT ALL PRIVILEGES ON DATABASE "kodekloud_db7" to kodekloud_joy;`  

`\q`
