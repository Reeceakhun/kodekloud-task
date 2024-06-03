kickstart the process, they're creating cron jobs in the Kubernetes cluster with placeholder commands. Follow the instructions below:



Create a cronjob named devops.


Set Its schedule to something like */10 * * * *. You can set any schedule for now.


Name the container cron-devops.


Utilize the httpd image with latest tag (specify as httpd:latest).


Execute the dummy command echo Welcome to xfusioncorp!.


Ensure the restart policy is OnFailure.


Note: The kubectl utility on jump_host is configured to work with the kubernetes cluster.  

# Solution
Create a .yaml file   
`vi devops-cronjob.yaml`   

Apply the configuration   
`kubectl apply -f devops-cronjob.yaml`    

Confirm cronjob was created  
`kubectl get cronjob devops`  
