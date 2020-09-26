# Stage 0, "build-stage"

FROM node:stretch-slim 
# Create app directory
WORKDIR /usr/src/app
COPY package*.json ./
ADD ./server/ ./
RUN npm install
EXPOSE 3000
CMD [ "npm", "start" ]



