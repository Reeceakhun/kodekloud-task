The Nautilus DevOps team is delving into Kubernetes for app management. One team member needs to create a deployment following these details:


Create a deployment named httpd to deploy the application httpd using the image httpd:latest (ensure to specify the tag)

Note: The kubectl utility on jump_host is set up to interact with the Kubernetes cluster.

# Solution

Create a .yaml file  
`vi httpd-deployment.yaml`   

Apply the configuration  
`kubectl apply -f httpd-deployment.yaml`  
Confirm the deployment was created  
`kubectl get deployment` 
