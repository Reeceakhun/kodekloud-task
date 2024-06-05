There is a production deployment planned for next week. The Nautilus DevOps team wants to test the deployment update and rollback on Dev environment first so that they can identify the risks in advance. Below you can find more details about the plan they want to execute.



Create a namespace nautilus. Create a deployment called httpd-deploy under this new namespace, It should have one container called httpd, use httpd:2.4.28 image and 2 replicas. The deployment should use RollingUpdate strategy with maxSurge=1, and maxUnavailable=2. Also create a NodePort type service named httpd-service and expose the deployment on nodePort: 30008.


Now upgrade the deployment to version httpd:2.4.43 using a rolling update.


Finally, once all pods are updated undo the recent update and roll back to the previous/original version.


Note:

a. The kubectl utility on jump_host has been configured to work with the kubernetes cluster.

# Solution
 create a namespace called nautilus  
 `kubectl create namespace nautilus`  

 Create .yaml file  
 `vi deployment.yaml`

Apply the deployment & service   
`kubectl apply -f deployment.yaml`   
`kubectl apply -f deployment.yaml`  

Upgrade the deployment to use the httpd:2.4.43 image   
`kubectl set image deployment/httpd-deploy httpd=httpd:2.4.43 -n nautilus`   

Once all pods are updated, roll back to the previous version   
`kubectl rollout undo deployment/httpd-deploy -n nautilus`   

Check the Deployment Status   
`kubectl rollout status deployment/httpd-deploy -n nautilus`   

View Pod Logs   
`kubectl get pods -n nautilus`   
`kubectl logs <pod-name> -n nautilus`   

Ensure Rollback Completed   
`kubectl describe deployment httpd-deploy -n nautilus`   
