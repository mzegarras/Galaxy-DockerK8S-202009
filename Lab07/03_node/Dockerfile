# Stage 0, "build-stage"

FROM node:12.18.4-alpine3.9
# Create app directory
WORKDIR /usr/src/app
COPY package*.json ./
ADD ./server/ ./
RUN npm install
EXPOSE 3000
CMD [ "npm", "start" ]



