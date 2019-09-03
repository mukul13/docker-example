FROM node:12.4.0
EXPOSE 4000

WORKDIR /home/server1

COPY package.json /home/server1/
COPY package-lock.json /home/server1/

RUN npm ci

COPY . /home/server1

RUN npm install

ADD https://github.com/ufoscout/docker-compose-wait/releases/download/2.2.1/wait /wait
RUN chmod +x /wait

## Launch the wait tool and then your application
CMD /wait && npm install && npm run start