FROM postgres:12

#COPY FICHERO CONF PASS
COPY ./files/pg_hba.conf /etc/postgresql/12/main/pg_hba.conf

#INSTALACION SQL
RUN apt-get update && \
    apt-get install -y --no-install-recommends && \
    apt-get install -y postgresql-12 && \
    apt-get install -y postgresql-client

#PORT
EXPOSE 5432
