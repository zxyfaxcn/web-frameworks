FROM perl:5.30-slim

RUN apt-get -qq update && \
  apt-get -qy install build-essential

WORKDIR /usr/src/app
COPY cpanfile d2app.psgi ./
RUN cpanm --installdeps .

EXPOSE 3000
CMD plackup -s Gazelle --port 3000 --env production --app d2app.psgi
