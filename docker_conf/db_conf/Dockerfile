FROM postgres:13

RUN apt update && apt -y upgrade 

RUN apt -y install build-essential libmsgpack-dev libgroonga-dev postgresql-server-dev-13 wget

RUN wget https://packages.groonga.org/debian/groonga-apt-source-latest-bullseye.deb
RUN apt install -y -V ./groonga-apt-source-latest-bullseye.deb

RUN echo "deb http://apt.postgresql.org/pub/repos/apt/ bullseye-pgdg main" | tee /etc/apt/sources.list.d/pgdg.list

RUN wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add -
RUN apt update && apt install -y -V postgresql-13-pgdg-pgroonga

ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=himitu
ENV POSTGRES_DB=flask_shopping

WORKDIR /root
ADD ./*.sql /root/