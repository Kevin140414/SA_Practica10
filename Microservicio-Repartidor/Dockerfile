FROM node
WORKDIR /App
ADD . /App
RUN npm install
ENV PORT 3002
ENV IP "172.10.10.13"
CMD ["node","/App/index.js"]
