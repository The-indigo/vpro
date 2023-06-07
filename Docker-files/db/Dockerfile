FROM mysql:8.0.33
LABEL "Project"="VPROFILE"
LABEL "Author"="Adeyemi"

#will be overwritten on docker run image
ENV MYSQL_ROOT_PASSWORD="ordinarypassword"
ADD db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql