FROM debian:11

RUN apt-get update -yq \
&& apt-get install curl gnupg -yq \
&& curl -sL https://deb.nodesource.com/setup_10.x | bash \
&& apt-get install nodejs npm -yq \
&& apt-get install nginx -yq \
&& apt-get clean -y

ADD . /app/
WORKDIR /app

RUN npm install

EXPOSE 8080
VOLUME /app/logs

CMD npm run start
