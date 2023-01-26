### Choice of the Kubernetes Objects ###

In the case of the client and backend services, i used Deployment objects to manage the desired state of the pods and ensure that the application is running as expected. Deployments provide features such as rolling updates, rollbacks, and auto-scaling, which make it easier to manage and maintain the application.

For the database , statefulSets provide features such as stable network identities and persistent storage, which are important for maintaining the integrity of the database.


### Method used to expose your pods to internet traffic ###
The method used to expose the pods to internet traffic is to create a service of type LoadBalancer. This method is commonly used to expose pods to external traffic because it provides a stable external IP address that routes traffic to the pods

### Good practices such as Docker image tag naming standards for ease of identification and personalization of images and containers.###
tagged my image according to semver conventions

api image = kubecmt/yolo_client:1.0
client image = kubecmt/yolo_client:1.0
mongo image = mongo:latest
