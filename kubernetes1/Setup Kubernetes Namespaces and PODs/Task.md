The Nautilus DevOps team is planning to deploy some micro services on Kubernetes platform. The team has already set up a Kubernetes cluster and now they want to set up some namespaces, deployments etc. Based on the current requirements, the team has shared some details as below:


Create a namespace named dev and deploy a POD within it. Name the pod dev-nginx-pod and use the nginx image with the latest tag. Ensure to specify the tag as nginx:latest.

Note: The kubectl utility on jump_host is configured to operate with the Kubernetes cluster.

# Solution
Create the .yaml files and copy in the respective contents  
`vi namespace.yaml`    
`vi dev-nginx.yaml`    
 
 Apply this configuration. Ensure to perform this accordingly    
`kubectl apply -f namespace.yaml`    
`kubectl apply -f dev-nginx.yaml`   

