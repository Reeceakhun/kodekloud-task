The Nautilus DevOps team is diving into Kubernetes for application management. One team member has a task to create a pod according to the details below:  
Create a pod named pod-httpd using the httpd image with the latest tag. Ensure to specify the tag as httpd:latest.

Set the app label to httpd_app, and name the container as httpd-container.

Note: The kubectl utility on jump_host


# Solution
Create a .yaml file  
`vi pod-httpd.yaml`   

Apply the configuration
`kubectl apply -f pod-httpd.yaml`  

Confirm the pod was created  
`kubectl get pods`  


