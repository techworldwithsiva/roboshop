FROM node:14
EXPOSE 8080
RUN adduser --system cart
USER cart
WORKDIR /opt/server
COPY package.json /opt/server/

RUN npm install

COPY server.js /opt/server/

CMD ["node", "server.js"]

