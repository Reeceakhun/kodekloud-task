The Nautilus DevOps team is gearing up to deploy applications on a Kubernetes cluster for migration purposes. A team member has been tasked with creating a ReplicaSet outlined below:



Create a ReplicaSet using httpd image with latest tag (ensure to specify as httpd:latest) and name it httpd-replicaset.


Apply labels: app as httpd_app, type as front-end.


Name the container httpd-container. Ensure the replica count is 4.


Note: The kubectl utility on jump_host is set up to interact with the Kubernetes cluster.

# Solution  
Create a .yaml file   
`vi httpd-replicaset.yaml`    
Apply the configuration   
`kubectl apply -f httpd-replicaset.yaml`    

Confirm  
`kubectl get rs`   
`kubectl get pods`  
