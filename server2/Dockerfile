FROM node:12.4.0
EXPOSE 3001

WORKDIR /home/server2

COPY package.json /home/server2/
COPY package-lock.json /home/server2/

RUN npm ci

COPY . /home/server2

ADD https://github.com/ufoscout/docker-compose-wait/releases/download/2.2.1/wait /wait
RUN chmod +x /wait

## Launch the wait tool and then your application
CMD /wait && npm install && npm run start