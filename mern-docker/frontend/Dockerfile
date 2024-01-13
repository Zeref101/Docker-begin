# set the base image to create the image for react app
FROM node:20-alpine

RUN addgroup app && adduser -S -G app app

# set the user to run the app
USER app

# set the working directory to /app
WORKDIR /app
COPY package*.json ./
USER root
# chown command changes the user and/or group ownership of for given file.
RUN chown -R app:app .

# change the user back to the app user
USER app

# install dependencies
RUN npm install

COPY . .
EXPOSE 5173

CMD npm run dev