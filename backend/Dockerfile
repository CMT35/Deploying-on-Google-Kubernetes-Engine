# Define base image
FROM node:14.18.2-alpine

# Define working directory
WORKDIR /microservice

# Copy package and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies 
RUN npm install

# copy rest of the app to the working directory
COPY . .

# expose port 5000
EXPOSE 5000

# Define entry point
CMD [ "npm", "start" ]