# 1. choice of base image

I chose alpine as my base image as it small, security-oriented, lightweight 

# 2.Dockerfile directives used in the creation and running of each container
Define base image
FROM node:14.18.2-alpine

Define working directory
WORKDIR /microservice

Copy package and package-lock.json to the working directory
COPY package*.json ./

Install dependencies 
RUN npm install

copy rest of the app to the working directory
COPY . .

expose port 5000
EXPOSE 5000

Define entry point
CMD [ "npm", "start" ]

# 3.Docker-compose Networking (Application port allocation and a bridge network implementation) 
for the api, i used port 5000 as it is allocated in the package.json and defined in the server.js
for the client side, i used port 3000 as allocated in the package,json file

# 4. Docker-compose volume definition and usage (where necessary).
i defined yolomy as my volume, as it is important to persist data, once the mongo container seizes to exist

# 5. Git workflow used to achieve the task.
git add . (to stage the changes)
git commit -m '<message>' (to commit the changes and labelling with the appropriate messages)
git push origin master (to push to my forked app repo)

# 6. Good practices such as Docker image tag naming standards for ease of identification of images and containers. 

tagged my image according to semver conventions
- api image = kubecmt/yolo_client:1.0
- client image = kubecmt/yolo_client:1.0
- mongo image = mongo:latest

# 7.Successful running of the applications and if not, debugging measures applied.
failed to connect to mongo server successfully
tried to reconfigure the server.js file with the correct credentials, yet to succeed

# 8. Successfully pushed to all images to dockerhub