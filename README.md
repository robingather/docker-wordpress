# Welcome

This is a wordpress implementation with docker-compose. It can run multiple wordpress sites on one server, each with phpmyadmin. They all run behind an nginx proxy server container using an automated letsencrypt implementation. After weeks of strife, this is perfection.

## How to use
1. pull this repo
2. copy the files into a working directory of your choice
3. copy site_example folder to make site_example1, site_example2, etc.
4. edit each .env file and change attributes to your liking.
5. docker-compose up the proxy server and then you can compose up or down whichever sites you wish.

## How to backup
1. go to host_ip:{$PHPMYADMIN_PORT} and export the db_example database to sql format.
2. copy the wp-content folder to a safe location, perhaps via FTP.

## How to restore backup or import pre-existing site
1. remove all content of wp-content (rm -r wp-content/*)
2. copy new content folder in (cp -r wp-content site_example/)

3. go to host_ip:{$PHPMYADMIN_PORT}, log in as root, select the db_example database, go to operations, and drop (delete) database.
4. go to import and upload the new database in sql format.
