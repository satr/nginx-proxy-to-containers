FROM node:14

WORKDIR /app
COPY app/package*.json ./
RUN npm install
COPY ./app .

EXPOSE 8001
#Main command of the container
CMD node server.js

#Addition port, exposing target folder (in this example folder: "/app"). This command also contains "Main command of the container": "node server.js"
EXPOSE 8002
RUN apt-get update && apt-get install python3 -y && echo "#!/bin/bash \n cd /app \n python3 -m http.server 8002 & \n node server.js" > run.sh; chmod +x run.sh
#Option for "node" images (to avoid installing Python):
#RUN npm install -g glance && echo "#!/bin/bash \n glance -d /app -p 8002 & \n node server.js" > run.sh; chmod +x run.sh

CMD ./run.sh
