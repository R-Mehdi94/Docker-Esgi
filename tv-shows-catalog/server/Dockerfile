# Créer un Dockerfile pour cette application en mode production
FROM node:20-alpine

COPY . /usr/src/app
WORKDIR /usr/src/app
RUN npm install 
RUN npm run build 
RUN npx prisma generate
CMD ["node","dist/main.js"]
