Earlier today, the Nautilus DevOps team deployed a new release for an application. However, a customer has reported a bug related to this recent release. Consequently, the team aims to revert to the previous version.


There exists a deployment named nginx-deployment; initiate a rollback to the previous revision.

Note: The kubectl utility on jump_host is configured to interact with the Kubernetes cluster.



# Solution  
Rollback to version nginx-deployment     
`kubectl rollout undo deployment/nginx-deployment`    
verify the rollback    
`kubectl rollout status deployment/nginx-deployment`     
