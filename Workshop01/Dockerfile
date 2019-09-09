# LOAD Base image of version latest
# In this case it is a node.js file
FROM node:latest

# LABEL 
LABEL "name"="northwindapp"

# SPECIFY environment variables
ENV DB_HOST=mydb DB_PORT=3306
ENV APP_PORT=3000 APP_DIR=/app

#Set the working directory
WORKDIR ${APP_DIR}

# Adds required files & folders into the image
ADD main.js .
ADD package.json .
ADD package-lock.json .
ADD config config
ADD public public
ADD views views

# Install dependencies
RUN npm install

# Expose the port 3000 for the app
EXPOSE ${APP_PORT}

#Start the app
ENTRYPOINT [ "node", "main.js" ]