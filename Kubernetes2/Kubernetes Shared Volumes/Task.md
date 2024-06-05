We are working on an application that will be deployed on multiple containers within a pod on Kubernetes cluster. There is a requirement to share a volume among the containers to save some temporary data. The Nautilus DevOps team is developing a similar template to replicate the scenario. Below you can find more details about it.



Create a pod named volume-share-xfusion.


For the first container, use image ubuntu with latest tag only and remember to mention the tag i.e ubuntu:latest, container should be named as volume-container-xfusion-1, and run a sleep command for it so that it remains in running state. Volume volume-share should be mounted at path /tmp/news.


For the second container, use image ubuntu with the latest tag only and remember to mention the tag i.e ubuntu:latest, container should be named as volume-container-xfusion-2, and again run a sleep command for it so that it remains in running state. Volume volume-share should be mounted at path /tmp/demo.


Volume name should be volume-share of type emptyDir.


After creating the pod, exec into the first container i.e volume-container-xfusion-1, and just for testing create a file news.txt with any content under the mounted path of first container i.e /tmp/news.


The file news.txt should be present under the mounted path /tmp/demo on the second container volume-container-xfusion-2 as well, since they are using a shared volume.


Note: The kubectl utility on jump_host has been configured to work with the kubernetes cluster.


# Solution
Create the YAML configuration:
Create the YAML file named volume-share-xfusion.yaml.  
`vi volume-share-xfusion.yaml`  

Create the Pod  
`kubectl apply -f volume-share-xfusion.yaml`  

Verify the Pod  
`kubectl get pods`  

Exec into the first container and create the *news.txt* file.   
`kubectl exec -it volume-share-xfusion -c volume-container-xfusion-1 -- bash`  
`echo "Hello from container 1" > /tmp/news/news.txt`  
`exit`  

Exec into the second container and check for the presence of *news.txt*.   
`kubectl exec -it volume-share-xfusion -c volume-container-xfusion-2 -- bash`  
`cat /tmp/demo/news.txt`  
