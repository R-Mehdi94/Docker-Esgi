# Créer un Dockerfile pour cette application en mode production
FROM node:20-alpine

COPY . /usr/src/app
WORKDIR /usr/src/app
RUN npm install 
CMD ["node","dist/main.js"]
