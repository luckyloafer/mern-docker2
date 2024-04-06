# set the base image to create the image for react app
FROM node:20-alpine


# RUN addgroup app && adduser -S -G app app


# USER app


WORKDIR /app

# copy package.json and package-lock.json to the working directory
# This is done before copying the rest of the files to take advantage of Docker’s cache
# If the package.json and package-lock.json files haven’t changed, Docker will use the cached dependencies
COPY package*.json ./


# USER root


# RUN chown -R app:app .


# USER app

# install dependencies
RUN npm install

# copy the rest of the files to the working directory
COPY . .

# expose port 5173 to tell Docker that the container listens on the specified network ports at runtime
EXPOSE 8000

# command to run the app
CMD npm start